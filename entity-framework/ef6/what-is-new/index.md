---
title: Новые возможности EF6
author: divega
ms.date: 2016-10-23
ms.prod: entity-framework
ms.author: divega
ms.manager: avickers
ms.technology: entity-framework-6
ms.topic: article
ms.assetid: 41d1f86b-ce66-4bf2-8963-48514406fb4c
caps.latest.revision: 3
ms.openlocfilehash: dba6403fa341e1abfe8da488a19cf8520e3ea574
ms.sourcegitcommit: 390f3a37bc55105ed7cc5b0e0925b7f9c9e80ba6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2018
ms.locfileid: "37914180"
---
# <a name="whats-new-in-ef6"></a><span data-ttu-id="8de62-102">Новые возможности EF6</span><span class="sxs-lookup"><span data-stu-id="8de62-102">What's New in EF6</span></span>

<span data-ttu-id="8de62-103">Корпорация Майкрософт настоятельно рекомендует использовать последнюю выпущенную версию Entity Framework, чтобы вы могли использовать новые функции с высочайшим уровнем надежности.</span><span class="sxs-lookup"><span data-stu-id="8de62-103">We highly recommend that you use the latest released version of Entity Framework to ensure you get the latest features and the highest stability.</span></span>
<span data-ttu-id="8de62-104">Тем не менее мы понимаем, что вам может потребоваться предыдущая версия или вы захотите поэкспериментировать с новыми усовершенствованиями в последнем предварительном выпуске.</span><span class="sxs-lookup"><span data-stu-id="8de62-104">However, we realize that you may need to use a previous version, or that you may want to experiment with new improvements in the latest pre-release.</span></span>
<span data-ttu-id="8de62-105">Чтобы установить определенные версии EF, см. сведения в разделе о [получении Entity Framework](~/ef6/fundamentals/install.md).</span><span class="sxs-lookup"><span data-stu-id="8de62-105">To install specific versions of EF, see [Get Entity Framework](~/ef6/fundamentals/install.md).</span></span>

<span data-ttu-id="8de62-106">На этой странице приводятся функции, которые включены в каждый новый выпуск.</span><span class="sxs-lookup"><span data-stu-id="8de62-106">This page documents the features that are included on each new release.</span></span>

## <a name="recent-releases"></a><span data-ttu-id="8de62-107">Последние выпуски</span><span class="sxs-lookup"><span data-stu-id="8de62-107">Recent releases</span></span>

### <a name="ef-tools-update-in-visual-studio-2017-157"></a><span data-ttu-id="8de62-108">Обновления инструментов для Entity Framework в Visual Studio 2017 версии 15.7</span><span class="sxs-lookup"><span data-stu-id="8de62-108">EF Tools Update in Visual Studio 2017 15.7</span></span>

<span data-ttu-id="8de62-109">В мае 2018 г. мы выпустили обновленную версию EF Tools в составе Visual Studio 2017 версии 15.7.</span><span class="sxs-lookup"><span data-stu-id="8de62-109">In May 2018, we released an updated version of the EF Tools as part of Visual Studio 2017 15.7.</span></span>
<span data-ttu-id="8de62-110">Она содержит ряд улучшений по частым проблемным вопросам.</span><span class="sxs-lookup"><span data-stu-id="8de62-110">It includes improvements for some common pain points:</span></span>

- <span data-ttu-id="8de62-111">Исправлено несколько ошибок в специальных возможностях пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8de62-111">Fixes for several user interface accessibility bugs</span></span>
- <span data-ttu-id="8de62-112">Создано обходное решение для проблемы с медленной работой SQL Server при создании моделей из существующих баз данных [#4](https://github.com/aspnet/entityframework6/issues/4).</span><span class="sxs-lookup"><span data-stu-id="8de62-112">Workaround for SQL Server performance regression when generating models from existing databases [#4](https://github.com/aspnet/entityframework6/issues/4)</span></span>
- <span data-ttu-id="8de62-113">Улучшена поддержка обновления моделей большого размера из SQL Server [#185](https://github.com/aspnet/EntityFramework6/issues/185).</span><span class="sxs-lookup"><span data-stu-id="8de62-113">Support for updating models for larger models on SQL Server [#185](https://github.com/aspnet/EntityFramework6/issues/185)</span></span>

<span data-ttu-id="8de62-114">Другим улучшением новой версии EF Tools является автоматическая установка среды выполнения EF 6.2 при создании модели в новом проекте.</span><span class="sxs-lookup"><span data-stu-id="8de62-114">Another improvement in this this new version of EF Tools is that it installs the EF 6.2 runtime when creating a model in a new project.</span></span> <span data-ttu-id="8de62-115">В предыдущих версиях Visual Studio среду выполнения EF 6.2 (а также любую более раннюю версию EF) можно использовать, установив соответствующую версию пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="8de62-115">With older versions of Visual Studio, it is possible to use the EF 6.2 runtime (as well as any past version of EF) by installing the corresponding version of the NuGet package.</span></span>

### <a name="ef-62-runtime"></a><span data-ttu-id="8de62-116">Среда выполнения EF 6.2</span><span class="sxs-lookup"><span data-stu-id="8de62-116">EF 6.2 Runtime</span></span>

<span data-ttu-id="8de62-117">Среда выполнения EF 6.2 была выпущена в NuGet в октябре 2017 г.</span><span class="sxs-lookup"><span data-stu-id="8de62-117">The EF 6.2 runtime was released to NuGet in October of 2017.</span></span>
<span data-ttu-id="8de62-118">Благодаря значительным усилиям нашего сообщества участников, вносящих вклад в разработку ресурсов с открытым исходным кодом, EF 6.2 содержит многочисленные [исправления ошибок](https://github.com/aspnet/entityframework6/issues?utf8=%E2%9C%93&q=is%3Aissue%20milestone%3A6.2.0%20is%3Aclosed%20label%3Aclosed-fixed%20-label%3Aarea-tools%20label%3Atype-bug) и [усовершенствования продуктов](https://github.com/aspnet/entityframework6/issues?utf8=%E2%9C%93&q=is%3Aissue%20milestone%3A6.2.0%20is%3Aclosed%20label%3Aclosed-fixed%20-label%3Aarea-tools%20label%3Atype-enhancement%20).</span><span class="sxs-lookup"><span data-stu-id="8de62-118">Thanks in great part to the efforts our community of open source contributors, EF 6.2 includes numerous [bugs fixes](https://github.com/aspnet/entityframework6/issues?utf8=%E2%9C%93&q=is%3Aissue%20milestone%3A6.2.0%20is%3Aclosed%20label%3Aclosed-fixed%20-label%3Aarea-tools%20label%3Atype-bug) and [product enhancements](https://github.com/aspnet/entityframework6/issues?utf8=%E2%9C%93&q=is%3Aissue%20milestone%3A6.2.0%20is%3Aclosed%20label%3Aclosed-fixed%20-label%3Aarea-tools%20label%3Atype-enhancement%20).</span></span>

<span data-ttu-id="8de62-119">Далее приведен краткий перечень наиболее важных изменений, затрагивающих среду выполнения EF 6.2.</span><span class="sxs-lookup"><span data-stu-id="8de62-119">Here is a brief list of the most important changes affecting the EF 6.2 runtime:</span></span>

- <span data-ttu-id="8de62-120">Сокращено время запуска за счет загрузки готовых моделей Code First из постоянного кэша [#275](https://github.com/aspnet/EntityFramework6/issues/275).</span><span class="sxs-lookup"><span data-stu-id="8de62-120">Reduce start up time by loading finished code first models from a persistent cache [#275](https://github.com/aspnet/EntityFramework6/issues/275)</span></span>
- <span data-ttu-id="8de62-121">Доступен текучий API для определения индексов [#274](https://github.com/aspnet/EntityFramework6/issues/274).</span><span class="sxs-lookup"><span data-stu-id="8de62-121">Fluent API to define indexes [#274](https://github.com/aspnet/EntityFramework6/issues/274)</span></span>
- <span data-ttu-id="8de62-122">DbFunctions.Like() для написания запросов LINQ, преобразующих LIKE в SQL [#241](https://github.com/aspnet/EntityFramework6/issues/241).</span><span class="sxs-lookup"><span data-stu-id="8de62-122">DbFunctions.Like() to enable writing LINQ queries that translate to LIKE in SQL [#241](https://github.com/aspnet/EntityFramework6/issues/241)</span></span>
- <span data-ttu-id="8de62-123">Migrate.exe теперь поддерживает параметр -script [#240](https://github.com/aspnet/EntityFramework6/issues/240).</span><span class="sxs-lookup"><span data-stu-id="8de62-123">Migrate.exe now supports -script option [#240](https://github.com/aspnet/EntityFramework6/issues/240)</span></span>
- <span data-ttu-id="8de62-124">EF6 теперь может работать со значениями ключей, созданными с помощью последовательности в SQL Server [#165](https://github.com/aspnet/EntityFramework6/issues/165).</span><span class="sxs-lookup"><span data-stu-id="8de62-124">EF6 can now work with key values generated by a sequence in SQL Server [#165](https://github.com/aspnet/EntityFramework6/issues/165)</span></span>
- <span data-ttu-id="8de62-125">Обновленный список временных ошибок для стратегии выполнения SQL Azure [#83](https://github.com/aspnet/EntityFramework6/issues/83).</span><span class="sxs-lookup"><span data-stu-id="8de62-125">Update list of transient errors for SQL Azure Execution Strategy [#83](https://github.com/aspnet/EntityFramework6/issues/83)</span></span>
- <span data-ttu-id="8de62-126">Ошибка. Повторное выполнение запросов или команд SQL завершается ошибкой The SqlParameter is already contained by another SqlParameterCollection ("Параметр SqlParameter уже содержится в другом объекте SqlParameterCollection") [#81](https://github.com/aspnet/EntityFramework6/issues/81).</span><span class="sxs-lookup"><span data-stu-id="8de62-126">Bug: Retrying queries or SQL commands fails with "The SqlParameter is already contained by another SqlParameterCollection" [#81](https://github.com/aspnet/EntityFramework6/issues/81)</span></span>
- <span data-ttu-id="8de62-127">Ошибка. Часто истекает время ожидания оценки DbQuery.ToString() в отладчике [#73](https://github.com/aspnet/EntityFramework6/issues/73).</span><span class="sxs-lookup"><span data-stu-id="8de62-127">Bug: Evaluation of DbQuery.ToString() frequently times out in the debugger [#73](https://github.com/aspnet/EntityFramework6/issues/73)</span></span>

## <a name="future-releases"></a><span data-ttu-id="8de62-128">Будущие выпуски</span><span class="sxs-lookup"><span data-stu-id="8de62-128">Future Releases</span></span>

<span data-ttu-id="8de62-129">Сведения о следующей версии EF6, см. в нашем [плане выпусков](roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="8de62-129">For information on future version of EF6, please look at our [Roadmap](roadmap.md).</span></span>

## <a name="past-releases"></a><span data-ttu-id="8de62-130">Прошлые выпуски</span><span class="sxs-lookup"><span data-stu-id="8de62-130">Past Releases</span></span>

<span data-ttu-id="8de62-131">На странице [прошлых выпусков](past-releases.md) содержится архив всех предыдущих версий EF и основных функций, которые были представлены в каждом выпуске.</span><span class="sxs-lookup"><span data-stu-id="8de62-131">The [Past Releases](past-releases.md) page contains an archive of all previous versions of EF and the major features that were introduced on each release.</span></span>