---
title: Перенос из EF6 в EF Core — перенос модели на основе кода — EF
author: rowanmiller
ms.date: 10/27/2016
ms.assetid: 2dce1a50-7d84-4856-abf6-2763dd9be99d
uid: efcore-and-ef6/porting/port-code
ms.openlocfilehash: 0a99eac2091c07d8bcf7d4e5e4bdc2afcaeee810
ms.sourcegitcommit: 9b562663679854c37c05fca13d93e180213fb4aa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "78413861"
---
# <a name="porting-an-ef6-code-based-model-to-ef-core"></a>Перенос модели на основе кода EF6 в EF Core

Если вы прочитали все предостережения и готовы к переносу, приведенные ниже рекомендации помогут вам начать.

## <a name="install-ef-core-nuget-packages"></a>Установка пакетов NuGet EF Core

Чтобы использовать EF Core, установите пакет NuGet для нужного поставщика базы данных. Например, при ориентации на SQL Server нужно установить `Microsoft.EntityFrameworkCore.SqlServer`. Дополнительные сведения см. в разделе [Поставщики баз данных](../../core/providers/index.md).

Если планируется использовать миграции, следует также установить пакет `Microsoft.EntityFrameworkCore.Tools`.

Можно оставить установленный пакет NuGet EF6 (EntityFramework), так как EF Core и EF6 могут использоваться параллельно в одном приложении. Однако если вы не планируете использовать EF6 в каких-либо областях приложения, то удаление пакета поможет вывести ошибки компиляции для фрагментов кода, требующих внимания.

## <a name="swap-namespaces"></a>Переключение пространств имен

Большинство API, используемых в EF6, находятся в пространстве имен `System.Data.Entity` (и связанных подпространствах имен). Первое изменение кода заключается в переключении на пространство имен `Microsoft.EntityFrameworkCore`. В общем случае вам следует начать с производного файла кода контекста, а затем действовать из него, устраняя ошибки компиляции по мере их возникновения.

## <a name="context-configuration-connection-etc"></a>Конфигурация контекста (подключение и т. п.)

Как описано в процедуре [проверки работы EF Core для приложения](ensure-requirements.md), EF Core использует меньше логики при обнаружении базы данных для подключения. Вам потребуется переопределить метод `OnConfiguring` в производном контексте и использовать API для конкретного поставщика базы данных для настройки подключения к базе данных.

Большинство приложений EF6 хранят строку подключения в файле `App/Web.config` приложения. В EF Core для считывания этой строки подключения используется API `ConfigurationManager`. Чтобы использовать этот API, может потребоваться добавить ссылку на сборку платформы `System.Configuration`.

``` csharp
public class BloggingContext : DbContext
{
    public DbSet<Blog> Blogs { get; set; }
    public DbSet<Post> Posts { get; set; }

    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
      optionsBuilder.UseSqlServer(ConfigurationManager.ConnectionStrings["BloggingDatabase"].ConnectionString);
    }
}
```

## <a name="update-your-code"></a>Обновление кода

На этом этапе осуществляется устранение ошибок компиляции и проверка кода, чтобы узнать, затронут ли вас изменения поведения.

## <a name="existing-migrations"></a>Существующие миграции

Фактически не существует практичного способа перенести имеющиеся миграции EF6 в EF Core.

По возможности лучше всего предположить, что все предыдущие миграции из EF6 были применены к базе данных, а затем начать миграцию схемы с этой точки с помощью EF Core. Для этого используйте команду `Add-Migration`, чтобы добавить миграцию после переноса модели в EF Core. Затем следует удалить весь код из методов `Up` и `Down` шаблонной миграции. Последующие миграции будут сравниваться с моделью после создания шаблона первоначальной миграции.

## <a name="test-the-port"></a>Тестирование переноса

Даже если приложение компилируется, это не означает, что оно успешно перенесено в EF Core. Необходимо протестировать все области приложения, чтобы предотвратить отсутствие неблагоприятного воздействия каких-либо изменений поведения.
