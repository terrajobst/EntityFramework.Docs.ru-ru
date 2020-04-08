---
title: Установка Entity Framework Core — EF Core
author: divega
ms.date: 08/06/2017
ms.assetid: 608cc774-c570-4809-8a3e-cd2c8446b8b2
uid: core/get-started/install/index
ms.openlocfilehash: 6575b1ac028f8b67b49ca7f4e49d6f19500be98f
ms.sourcegitcommit: 9b562663679854c37c05fca13d93e180213fb4aa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "80136169"
---
# <a name="installing-entity-framework-core"></a><span data-ttu-id="2cedc-102">Установка Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="2cedc-102">Installing Entity Framework Core</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2cedc-103">предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2cedc-103">Prerequisites</span></span>

* <span data-ttu-id="2cedc-104">EF Core — это библиотека [.NET Standard 2.0](/dotnet/standard/net-standard).</span><span class="sxs-lookup"><span data-stu-id="2cedc-104">EF Core is a [.NET Standard 2.0](/dotnet/standard/net-standard) library.</span></span> <span data-ttu-id="2cedc-105">Для запуска EF Core требуется реализация .NET, которая поддерживает .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="2cedc-105">So EF Core requires a .NET implementation that supports .NET Standard 2.0 to run.</span></span> <span data-ttu-id="2cedc-106">На EF Core также могут ссылаться другие библиотеки .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="2cedc-106">EF Core can also be referenced by other .NET Standard 2.0 libraries.</span></span>

* <span data-ttu-id="2cedc-107">Например, EF Core можно использовать для разработки приложений, предназначенных для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2cedc-107">For example, you can use EF Core to develop apps that target .NET Core.</span></span> <span data-ttu-id="2cedc-108">Для создания приложений .NET Core требуется [пакет SDK для .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="2cedc-108">Building .NET Core apps requires the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="2cedc-109">При необходимости также можно использовать среду разработки, например [Visual Studio](https://visualstudio.microsoft.com/vs), [Visual Studio для Mac](https://visualstudio.microsoft.com/vs/mac) или [Visual Studio Code](https://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="2cedc-109">Optionally, you can also use a development environment like [Visual Studio](https://visualstudio.microsoft.com/vs), [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac), or [Visual Studio Code](https://code.visualstudio.com).</span></span> <span data-ttu-id="2cedc-110">Дополнительные сведения см. в разделе [Приступая к работе с .NET Core](/dotnet/core/get-started).</span><span class="sxs-lookup"><span data-stu-id="2cedc-110">For more information, check [Getting Started with .NET Core](/dotnet/core/get-started).</span></span>

* <span data-ttu-id="2cedc-111">EF Core можно использовать для разработки приложений в Windows с использованием Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2cedc-111">You can use EF Core to develop applications on Windows using Visual Studio.</span></span> <span data-ttu-id="2cedc-112">Рекомендуется использовать последнюю версию [Visual Studio](https://visualstudio.microsoft.com/vs).</span><span class="sxs-lookup"><span data-stu-id="2cedc-112">The latest version of [Visual Studio](https://visualstudio.microsoft.com/vs) is recommended.</span></span>

* <span data-ttu-id="2cedc-113">EF Core можно запустить в других реализациях .NET, таких как [Xamarin](https://dotnet.microsoft.com/apps/xamarin) и .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2cedc-113">EF Core can run on other .NET implementations like [Xamarin](https://dotnet.microsoft.com/apps/xamarin) and .NET Native.</span></span> <span data-ttu-id="2cedc-114">Но на практике у этих реализаций есть ограничения среды выполнения, которые могут повлиять на то, насколько хорошо EF Core работает в приложении.</span><span class="sxs-lookup"><span data-stu-id="2cedc-114">But in practice those implementations have runtime limitations that may affect how well EF Core works on your app.</span></span> <span data-ttu-id="2cedc-115">Дополнительные сведения см. в разделе [Реализации .NET, поддерживаемые EF Core](xref:core/platforms/index).</span><span class="sxs-lookup"><span data-stu-id="2cedc-115">For more information, see [.NET implementations supported by EF Core](xref:core/platforms/index).</span></span>

* <span data-ttu-id="2cedc-116">Наконец, для различных поставщиков баз данных требуются различные версии ядер СУБД, реализаций .NET и операционных систем.</span><span class="sxs-lookup"><span data-stu-id="2cedc-116">Finally, different database providers may require specific database engine versions, .NET implementations, or operating systems.</span></span> <span data-ttu-id="2cedc-117">Убедитесь, что доступен [поставщик базы данных EF Core](xref:core/providers/index), поддерживающий подходящую среду для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="2cedc-117">Make sure an [EF Core database provider](xref:core/providers/index) is available that supports the right environment for your application.</span></span>

## <a name="get-the-entity-framework-core-runtime"></a><span data-ttu-id="2cedc-118">Получение среды выполнения Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="2cedc-118">Get the Entity Framework Core runtime</span></span>

<span data-ttu-id="2cedc-119">Чтобы добавить EF Core в приложение, установите пакет NuGet для поставщика базы данных, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="2cedc-119">To add EF Core to an application, install the NuGet package for the database provider you want to use.</span></span>

<span data-ttu-id="2cedc-120">Если вы создаете приложение ASP.NET Core, устанавливать поставщики в памяти и поставщики SQL Server не нужно.</span><span class="sxs-lookup"><span data-stu-id="2cedc-120">If you're building an ASP.NET Core application, you don't need to install the in-memory and SQL Server providers.</span></span> <span data-ttu-id="2cedc-121">Эти поставщики включены в текущие версии ASP.NET Core, а также в среду выполнения EF Core.</span><span class="sxs-lookup"><span data-stu-id="2cedc-121">Those providers are included in current versions of ASP.NET Core, alongside the EF Core runtime.</span></span>  

<span data-ttu-id="2cedc-122">Установить или обновить пакеты NuGet можно в интерфейсе командной строки (CLI) .NET Core, а также в диалоговом окне или консоли диспетчера пакетов Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2cedc-122">To install or update NuGet packages, you can use the .NET Core command-line interface (CLI), the Visual Studio Package Manager Dialog, or the Visual Studio Package Manager Console.</span></span>

### <a name="net-core-cli"></a><span data-ttu-id="2cedc-123">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="2cedc-123">.NET Core CLI</span></span>

* <span data-ttu-id="2cedc-124">Чтобы установить или обновить поставщик EF Core SQL Server, выполните следующую команду интерфейса командной строки .NET Core в командной строке операционной системы:</span><span class="sxs-lookup"><span data-stu-id="2cedc-124">Use the following .NET Core CLI command from the operating system's command line to install or update the EF Core SQL Server provider:</span></span>

  ```dotnetcli
  dotnet add package Microsoft.EntityFrameworkCore.SqlServer
  ```

* <span data-ttu-id="2cedc-125">Вы можете указать в команде `dotnet add package` конкретную версию, используя модификатор `-v`.</span><span class="sxs-lookup"><span data-stu-id="2cedc-125">You can indicate a specific version in the `dotnet add package` command, using the `-v` modifier.</span></span> <span data-ttu-id="2cedc-126">Например, чтобы установить пакеты EF Core 2.2.0, добавьте к команде `-v 2.2.0`.</span><span class="sxs-lookup"><span data-stu-id="2cedc-126">For example, to install EF Core 2.2.0 packages, append `-v 2.2.0` to the command.</span></span>

<span data-ttu-id="2cedc-127">Дополнительные сведения см. в разделе [Средства интерфейса командной строки (CLI) .NET](/dotnet/core/tools/).</span><span class="sxs-lookup"><span data-stu-id="2cedc-127">For more information, see [.NET command-line interface (CLI) tools](/dotnet/core/tools/).</span></span>

### <a name="visual-studio-nuget-package-manager-dialog"></a><span data-ttu-id="2cedc-128">Диалоговое окно диспетчера пакетов NuGet в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2cedc-128">Visual Studio NuGet Package Manager Dialog</span></span>

* <span data-ttu-id="2cedc-129">В меню Visual Studio выберите **"Проект" > "Управление пакетами NuGet"** .</span><span class="sxs-lookup"><span data-stu-id="2cedc-129">From the Visual Studio menu, select **Project > Manage NuGet Packages**</span></span>

* <span data-ttu-id="2cedc-130">Нажмите кнопку **Обзор** или откройте вкладку **Обновления**.</span><span class="sxs-lookup"><span data-stu-id="2cedc-130">Click on the **Browse** or the **Updates** tab</span></span>

* <span data-ttu-id="2cedc-131">Чтобы установить или обновить поставщик SQL Server, выберите пакет `Microsoft.EntityFrameworkCore.SqlServer` и подтвердите свой выбор.</span><span class="sxs-lookup"><span data-stu-id="2cedc-131">To install or update the SQL Server provider, select the `Microsoft.EntityFrameworkCore.SqlServer` package, and confirm.</span></span>

<span data-ttu-id="2cedc-132">Дополнительные сведения: [Диалоговое окно диспетчера пакетов NuGet](/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="2cedc-132">For more information, see [NuGet Package Manager Dialog](/nuget/tools/package-manager-ui).</span></span>

### <a name="visual-studio-nuget-package-manager-console"></a><span data-ttu-id="2cedc-133">Консоль диспетчера пакетов NuGet в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2cedc-133">Visual Studio NuGet Package Manager Console</span></span>

* <span data-ttu-id="2cedc-134">В меню Visual Studio выберите **"Сервис" > "Диспетчер пакетов NuGet" > "Консоль диспетчера пакетов"** .</span><span class="sxs-lookup"><span data-stu-id="2cedc-134">From the Visual Studio menu, select **Tools > NuGet Package Manager > Package Manager Console**</span></span>

* <span data-ttu-id="2cedc-135">Чтобы установить поставщик SQL Server, в консоли диспетчера пакетов выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2cedc-135">To install the SQL Server provider, run the following command in the Package Manager Console:</span></span>

  ``` PowerShell  
  Install-Package Microsoft.EntityFrameworkCore.SqlServer
  ```

* <span data-ttu-id="2cedc-136">Чтобы обновить поставщик, используйте команду `Update-Package`.</span><span class="sxs-lookup"><span data-stu-id="2cedc-136">To update the provider, use the `Update-Package` command.</span></span>

* <span data-ttu-id="2cedc-137">Чтобы указать конкретную версию, используйте модификатор `-Version`.</span><span class="sxs-lookup"><span data-stu-id="2cedc-137">To specify a specific version, use the `-Version` modifier.</span></span> <span data-ttu-id="2cedc-138">Например, чтобы установить пакеты EF Core 2.2.0, добавьте в команды `-Version 2.2.0`.</span><span class="sxs-lookup"><span data-stu-id="2cedc-138">For example, to install EF Core 2.2.0 packages, append `-Version 2.2.0` to the commands</span></span>

<span data-ttu-id="2cedc-139">Дополнительные сведения: [Консоль диспетчера пакетов](/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="2cedc-139">For more information, see [Package Manager Console](/nuget/tools/package-manager-console).</span></span>

## <a name="get-the-entity-framework-core-tools"></a><span data-ttu-id="2cedc-140">Получение инструментов Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="2cedc-140">Get the Entity Framework Core tools</span></span>

<span data-ttu-id="2cedc-141">Вы можете установить инструменты для выполнения задач, связанных с EF Core, в своем проекте, таких как создание и применение миграций базы данных, а также создание модели EF Core на основе существующей базы данных.</span><span class="sxs-lookup"><span data-stu-id="2cedc-141">You can install tools to carry out EF Core-related tasks in your project, like creating and applying database migrations, or creating an EF Core model based on an existing database.</span></span>

<span data-ttu-id="2cedc-142">Доступно два набора инструментов:</span><span class="sxs-lookup"><span data-stu-id="2cedc-142">Two sets of tools are available:</span></span>

* <span data-ttu-id="2cedc-143">[Инструменты интерфейса командной строки (CLI)](xref:core/miscellaneous/cli/dotnet) .NET Core можно использовать в Windows, Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="2cedc-143">The [.NET Core command-line interface (CLI) tools](xref:core/miscellaneous/cli/dotnet) can be used on Windows, Linux, or macOS.</span></span> <span data-ttu-id="2cedc-144">Эти команды начинаются с `dotnet ef`.</span><span class="sxs-lookup"><span data-stu-id="2cedc-144">These commands begin with `dotnet ef`.</span></span>

* <span data-ttu-id="2cedc-145">[Инструменты консоли диспетчера пакетов](xref:core/miscellaneous/cli/powershell) работают в Visual Studio в Windows.</span><span class="sxs-lookup"><span data-stu-id="2cedc-145">The [Package Manager Console (PMC) tools](xref:core/miscellaneous/cli/powershell) run in Visual Studio on Windows.</span></span> <span data-ttu-id="2cedc-146">Эти команды начинаются с глагола, например `Add-Migration`, `Update-Database`.</span><span class="sxs-lookup"><span data-stu-id="2cedc-146">These commands start with a verb, for example `Add-Migration`, `Update-Database`.</span></span>

<span data-ttu-id="2cedc-147">Хотя вы можете использовать команды `dotnet ef` в консоли диспетчера пакетов, в Visual Studio рекомендуется использовать инструменты консоли диспетчера пакетов:</span><span class="sxs-lookup"><span data-stu-id="2cedc-147">Although you can also use the `dotnet ef` commands from the Package Manager Console, it's recommended to use the Package Manager Console tools when you're using Visual Studio:</span></span>

* <span data-ttu-id="2cedc-148">Они автоматически работают для выбранного в PMC проекта в Visual Studio без переключения каталогов вручную.</span><span class="sxs-lookup"><span data-stu-id="2cedc-148">They automatically work with the current project selected in the PMC in Visual Studio, without requiring manually switching directories.</span></span>  

* <span data-ttu-id="2cedc-149">Они автоматически открывают файлы, созданные командами в Visual Studio, после завершения соответствующей команды.</span><span class="sxs-lookup"><span data-stu-id="2cedc-149">They automatically open files generated by the commands in Visual Studio after the command is completed.</span></span>

<a name="cli"></a>

### <a name="get-the-net-core-cli-tools"></a><span data-ttu-id="2cedc-150">Получение инструментов CLI для .NET Core</span><span class="sxs-lookup"><span data-stu-id="2cedc-150">Get the .NET Core CLI tools</span></span>

<span data-ttu-id="2cedc-151">Для инструментов CLI .NET Core требуется пакет SDK для .NET Core, указанный ранее в разделе [Необходимые компоненты](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="2cedc-151">.NET Core CLI tools require the .NET Core SDK, mentioned earlier in [Prerequisites](#prerequisites).</span></span>

<span data-ttu-id="2cedc-152">Команды `dotnet ef` входят в текущие версии пакета SDK для .NET Core, но, чтобы включить их для конкретного проекта, нужно установить пакет `Microsoft.EntityFrameworkCore.Design`:</span><span class="sxs-lookup"><span data-stu-id="2cedc-152">The `dotnet ef` commands are included in current versions of the .NET Core SDK, but to enable the commands on a specific project, you have to install the `Microsoft.EntityFrameworkCore.Design` package:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore.Design
```

> [!IMPORTANT]
> <span data-ttu-id="2cedc-153">Всегда используйте версии пакетов инструментов, которые соответствуют основному номеру версии для пакетов среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2cedc-153">Always use the version of the tools package that matches the major version of the runtime packages.</span></span>

### <a name="get-the-package-manager-console-tools"></a><span data-ttu-id="2cedc-154">Получение инструментов консоли диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="2cedc-154">Get the Package Manager Console tools</span></span>

<span data-ttu-id="2cedc-155">Чтобы получить инструменты консоли диспетчера пакетов для EF Core, установите пакет `Microsoft.EntityFrameworkCore.Tools`.</span><span class="sxs-lookup"><span data-stu-id="2cedc-155">To get the Package Manager Console tools for EF Core, install the `Microsoft.EntityFrameworkCore.Tools` package.</span></span> <span data-ttu-id="2cedc-156">Например, в Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="2cedc-156">For example, from Visual Studio:</span></span>

``` PowerShell
Install-Package Microsoft.EntityFrameworkCore.Tools
```

<span data-ttu-id="2cedc-157">Этот пакет автоматически включается в приложения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2cedc-157">For ASP.NET Core apps, this package is included automatically.</span></span>

## <a name="upgrading-to-the-latest-ef-core"></a><span data-ttu-id="2cedc-158">Обновление до последней версии EF Core</span><span class="sxs-lookup"><span data-stu-id="2cedc-158">Upgrading to the latest EF Core</span></span>

* <span data-ttu-id="2cedc-159">Каждый раз при выпуске новой версии EF Core мы также выпускаем новую версию поставщиков, которые входят в проект EF Core, например Microsoft.EntityFrameworkCore.SqlServer, Microsoft.EntityFrameworkCore.Sqlite и Microsoft.EntityFrameworkCore.InMemory.</span><span class="sxs-lookup"><span data-stu-id="2cedc-159">Any time we release a new version of EF Core, we also release a new version of the providers that are part of the EF Core project, like Microsoft.EntityFrameworkCore.SqlServer, Microsoft.EntityFrameworkCore.Sqlite, and Microsoft.EntityFrameworkCore.InMemory.</span></span> <span data-ttu-id="2cedc-160">Кроме того, можно просто обновить поставщик до новой версии, чтобы получить все улучшения.</span><span class="sxs-lookup"><span data-stu-id="2cedc-160">You can just upgrade to the new version of the provider to get all the improvements.</span></span>

* <span data-ttu-id="2cedc-161">EF Core вместе с поставщиками SQL Server и поставщиками в памяти включены в текущие версии ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2cedc-161">EF Core, together with the SQL Server and the in-memory providers are included in current versions of ASP.NET Core.</span></span> <span data-ttu-id="2cedc-162">Чтобы обновить существующее приложение до более новой версии EF Core, всегда обновляйте версию ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2cedc-162">To upgrade an existing ASP.NET Core application to a newer version of EF Core, always upgrade the version of ASP.NET Core.</span></span>

* <span data-ttu-id="2cedc-163">Если требуется обновить приложение, использующее сторонний поставщик базы данных, всегда ищите обновление поставщика, совместимое с нужной вам версией EF Core.</span><span class="sxs-lookup"><span data-stu-id="2cedc-163">If you need to update an application that is using a third-party database provider, always check for an update of the provider that is compatible with the version of EF Core you want to use.</span></span> <span data-ttu-id="2cedc-164">Например, поставщики баз данных для предыдущих версий несовместимы с версией 2.0 среды выполнения EF Core.</span><span class="sxs-lookup"><span data-stu-id="2cedc-164">For example, database providers for previous versions are not compatible with version 2.0 of the EF Core runtime.</span></span>

* <span data-ttu-id="2cedc-165">Сторонние поставщики EF Core обычно не выпускают исправления вместе со средой выполнения EF Core.</span><span class="sxs-lookup"><span data-stu-id="2cedc-165">Third-party providers for EF Core usually don't release patch versions alongside the EF Core runtime.</span></span> <span data-ttu-id="2cedc-166">Чтобы обновить приложение, использующее сторонний поставщик, до версии исправления EF Core, может потребоваться добавить прямую ссылку на отдельные компоненты EF Core, такие как Microsoft.EntityFrameworkCore и Microsoft.EntityFrameworkCore.Relational.</span><span class="sxs-lookup"><span data-stu-id="2cedc-166">To upgrade an application that uses a third-party provider to a patch version of EF Core, you may need to add a direct reference to individual EF Core runtime components, such as Microsoft.EntityFrameworkCore, and Microsoft.EntityFrameworkCore.Relational.</span></span>

* <span data-ttu-id="2cedc-167">При обновлении существующего приложения до последней версии EF Core некоторые ссылки на более старые пакеты EF Core, возможно, потребуется удалить вручную:</span><span class="sxs-lookup"><span data-stu-id="2cedc-167">If you're upgrading an existing application to the latest version of EF Core, some references to older EF Core packages may need to be removed manually:</span></span>

  * <span data-ttu-id="2cedc-168">Пакеты поставщиков баз данных, используемые во время разработки, например `Microsoft.EntityFrameworkCore.SqlServer.Design`, больше не требуются и не поддерживаются в EF Core 2.0 и более поздних версиях, но они не удаляются автоматически при обновлении других пакетов.</span><span class="sxs-lookup"><span data-stu-id="2cedc-168">Database provider design-time packages such as `Microsoft.EntityFrameworkCore.SqlServer.Design` are no longer required or supported from EF Core 2.0 and later, but aren't automatically removed when upgrading the other packages.</span></span>

  * <span data-ttu-id="2cedc-169">Инструменты .NET CLI включены в пакет SDK для .NET версии 2.1, поэтому ссылку на этот пакет можно удалить из файла проекта:</span><span class="sxs-lookup"><span data-stu-id="2cedc-169">The .NET CLI tools are included in the .NET SDK since version 2.1, so the reference to that package can be removed from the project file:</span></span>

    ``` xml
    <DotNetCliToolReference Include="Microsoft.EntityFrameworkCore.Tools.DotNet" Version="2.0.0" />
    ```
