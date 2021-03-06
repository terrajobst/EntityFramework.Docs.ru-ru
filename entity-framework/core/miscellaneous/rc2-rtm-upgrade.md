---
title: Обновление с EF Core 1,0 RC2 до RTM — EF Core
author: rowanmiller
ms.date: 10/27/2016
ms.assetid: c3c1940b-136d-45d8-aa4f-cb5040f8980a
uid: core/miscellaneous/rc2-rtm-upgrade
ms.openlocfilehash: 779caad7883d13684b389dab7515be44bc42e1ef
ms.sourcegitcommit: cc0ff36e46e9ed3527638f7208000e8521faef2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78414041"
---
# <a name="upgrading-from-ef-core-10-rc2-to-rtm"></a>Обновление с EF Core 1,0 от RC2 до RTM

В этой статье приводятся рекомендации по перемещению приложения, созданного с помощью пакетов RC2, в 1.0.0 RTM.

## <a name="package-versions"></a>Версии пакета

Имена пакетов верхнего уровня, которые обычно устанавливаются в приложение, не изменились между RC2 и RTM.

**Необходимо обновить установленные пакеты до версий RTM:**

* Пакеты среды выполнения (например, `Microsoft.EntityFrameworkCore.SqlServer`) изменились с `1.0.0-rc2-final` на `1.0.0`.

* Пакет `Microsoft.EntityFrameworkCore.Tools` изменен с `1.0.0-preview1-final` на `1.0.0-preview2-final`. Обратите внимание, что инструментарий по-прежнему является предварительным выпуском.

## <a name="existing-migrations-may-need-maxlength-added"></a>Для существующих миграций может потребоваться добавить maxLength

В RC2 определение столбца в процессе миграции выглядит так, как `table.Column<string>(nullable: true)`, а длина столбца была просмотрена в некоторых метаданных, которые хранятся в коде, который находится за миграцией. В RTM длина теперь включается в шаблонный код `table.Column<string>(maxLength: 450, nullable: true)`.

Для всех существующих миграций, сформированных до использования RTM, не будет указан аргумент `maxLength`. Это означает, что будет использоваться максимальная длина, поддерживаемая базой данных (`nvarchar(max)` в SQL Server). Это может быть удобно для некоторых столбцов, но столбцы, которые являются частью ключа, внешнего ключа или индекса, должны быть обновлены для включения максимальной длины. По соглашению 450 — это максимальная длина, используемая для ключей, внешних ключей и индексированных столбцов. Если вы явно настроили длину в модели, вместо нее следует использовать эту длину.

### <a name="aspnet-identity"></a>ASP.NET Identity

Это изменение влияет на проекты, использующие ASP.NET Identity и созданные из шаблона проекта предварительной версии RTM. Шаблон проекта включает миграцию, используемую для создания базы данных. Эту миграцию необходимо изменить, чтобы указать максимальную длину `256` для следующих столбцов.

* **аспнетролес**
  * Имя
  * нормализеднаме
* **AspNetUsers**
  * Email
  * нормализедемаил
  * нормализедусернаме
  * UserName

Если не выполнить это изменение, при первоначальной миграции к базе данных будет получено следующее исключение.

``` Console
System.Data.SqlClient.SqlException (0x80131904): Column 'NormalizedName' in table 'AspNetRoles' is of a type that is invalid for use as a key column in an index.
```

## <a name="net-core-remove-imports-in-projectjson"></a>.NET Core: удаление "Imports" в Project. JSON

Если вы намерены ориентироваться на .NET Core с RC2, вам нужно было добавить `imports` в Project. JSON в качестве временного решения для некоторых зависимостей EF Core, не поддерживающих .NET Standard. Теперь их можно удалить.

``` json
{
  "frameworks": {
    "netcoreapp1.0": {
      "imports": ["dnxcore50", "portable-net451+win8"]
    }
  }
}
```

> [!NOTE]  
> Начиная с версии 1,0 RTM, [пакет SDK для .NET Core](https://www.microsoft.com/net/download/core) больше не поддерживает `project.json` или разработку приложений .NET Core с помощью Visual Studio 2015. Корпорация Майкрософт рекомендует [выполнить миграцию project.json в формат csproj](https://docs.microsoft.com/dotnet/articles/core/migration/). При использовании Visual Studio рекомендуется выполнить обновление до [Visual studio 2017](https://www.visualstudio.com/downloads/).

## <a name="uwp-add-binding-redirects"></a>UWP: Добавление перенаправлений привязок

Попытка выполнить команды EF в проектах универсальная платформа Windows (UWP) приводит к следующей ошибке:

```output
System.IO.FileLoadException: Could not load file or assembly 'System.IO.FileSystem.Primitives, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference.
```

Необходимо вручную добавить перенаправления привязок в проект UWP. Создайте файл с именем `App.config` в корневой папке проекта и добавьте перенаправления к правильным версиям сборки.

```xml
<configuration>
 <runtime>
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
     <dependentAssembly>
       <assemblyIdentity name="System.IO.FileSystem.Primitives"
                         publicKeyToken="b03f5f7f11d50a3a"
                         culture="neutral" />
       <bindingRedirect oldVersion="4.0.0.0"
                        newVersion="4.0.1.0"/>
     </dependentAssembly>
     <dependentAssembly>
       <assemblyIdentity name="System.Threading.Overlapped"
                         publicKeyToken="b03f5f7f11d50a3a"
                         culture="neutral" />
       <bindingRedirect oldVersion="4.0.0.0"
                        newVersion="4.0.1.0"/>
     </dependentAssembly>
   </assemblyBinding>
 </runtime>
</configuration>
```
