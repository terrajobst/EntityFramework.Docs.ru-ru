---
title: Стратегия развития Entity Framework Core
author: divega
ms.author: divega
ms.date: 02/20/2018
ms.assetid: 834C9729-7F6E-4355-917D-DE3EE9FE149E
ms.technology: entity-framework-core
uid: core/what-is-new/roadmap
ms.openlocfilehash: 5aef679df2ecdfe7f59458c8994d0d17b4a889ff
ms.sourcegitcommit: 2ef0a4a90b01edd22b9206f8729b8de459ef8cab
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/20/2018
---
# <a name="entity-framework-core-roadmap"></a><span data-ttu-id="3b1f5-102">Стратегия развития Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="3b1f5-102">Entity Framework Core Roadmap</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b1f5-103">Обратите внимание на то, что наборы возможностей и расписания будущих выпусков могут быть изменены, и, несмотря на то, что мы стараемся поддерживать эту страницу в актуальном состоянии, в определенные моменты времени содержание страницы может не отражать наши текущие планы.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-103">Please note that the feature sets and schedules of future releases are always subject to change, and although we will try to keep this page up to date, it may not reflect our latest plans at all times.</span></span>

<span data-ttu-id="3b1f5-104">Первая предварительная версия EF Core 2.1 была выпущена в феврале 2018 года.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-104">The first preview of EF Core 2.1 was released on February 2018.</span></span> <span data-ttu-id="3b1f5-105">Дополнительные сведения об этом выпуске см. в статье [Новые возможности в EF Core 2.1](xref:core/what-is-new/ef-core-2.1).</span><span class="sxs-lookup"><span data-stu-id="3b1f5-105">You can now find more information about this release in [What is new in EF Core 2.1](xref:core/what-is-new/ef-core-2.1).</span></span>

<span data-ttu-id="3b1f5-106">Мы планируем выпускать дополнительные предварительные версии EF Core 2.1 ежемесячно, а выпуск окончательной версии намечен на второй квартал 2018 года.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-106">We intend to release additional previews of EF Core 2.1 monthly, and a final release on the second calendar quarter of 2018.</span></span>

<span data-ttu-id="3b1f5-107">Разработка [плана выпуска](#release-planning-process) для релиза, следующего за версией 2.1, еще не завершена.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-107">We have not completed the [release planning](#release-planning-process) for the next release after 2.1.</span></span>

## <a name="schedule"></a><span data-ttu-id="3b1f5-108">Расписание</span><span class="sxs-lookup"><span data-stu-id="3b1f5-108">Schedule</span></span>

<span data-ttu-id="3b1f5-109">Расписание выпусков EF Core синхронизируется с [расписанием .NET Core](https://github.com/dotnet/core/blob/master/roadmap.md) и [расписанием ASP.NET Core](https://github.com/aspnet/Home/wiki/Roadmap).</span><span class="sxs-lookup"><span data-stu-id="3b1f5-109">The schedule for EF Core is in-sync with the [.NET Core schedule](https://github.com/dotnet/core/blob/master/roadmap.md) and [ASP.NET Core schedule](https://github.com/aspnet/Home/wiki/Roadmap).</span></span>

## <a name="backlog"></a><span data-ttu-id="3b1f5-110">Невыполненная работа</span><span class="sxs-lookup"><span data-stu-id="3b1f5-110">Backlog</span></span>

<span data-ttu-id="3b1f5-111">Мы используем [контрольные точки невыполненной работы](https://github.com/aspnet/EntityFrameworkCore/issues?q=is%3Aopen+is%3Aissue+milestone%3ABacklog+sort%3Areactions-%2B1-desc) при отслеживании проблем для ведения подробного списка проблем и возможностей.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-111">We use the [Backlog Milestone](https://github.com/aspnet/EntityFrameworkCore/issues?q=is%3Aopen+is%3Aissue+milestone%3ABacklog+sort%3Areactions-%2B1-desc) in our issue tracker to maintain a detailed list of issues and features.</span></span> <span data-ttu-id="3b1f5-112">Клиенты могут комментировать и голосовать за них.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-112">Customers can comment and up-vote these.</span></span>

<span data-ttu-id="3b1f5-113">Как правило, мы не закрываем проблемы, которые мы рассчитываем когда-нибудь решить, или с которыми может справиться кто-то из сообщества, но это не означает намерения разрешить их за конкретный период времени до тех пор, пока мы не добавим их к определенной контрольной точке как часть [процесса планирования выпусков](#release-planning-process).</span><span class="sxs-lookup"><span data-stu-id="3b1f5-113">We tend to leave issues open that we reasonably expect we will work on at some point, or that someone from the community could tackle, but that does not imply the intent to resolve them in a specific timeframe until we assign them to a specific milestone as part of our [release planning process](#release-planning-process).</span></span>

<span data-ttu-id="3b1f5-114">Если мы не планируем когда-либо реализовать возможность, проблема, скорее всего, будет закрыта.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-114">If we do not plan to ever implement a feature, we will likely close the issue.</span></span> <span data-ttu-id="3b1f5-115">Закрытие проблемы может быть пересмотрено позднее, если у нас появятся новые сведения о ней.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-115">An issue that we closed can be reconsidered at a later point if we obtain new information about it.</span></span>

<span data-ttu-id="3b1f5-116">Другими словами, у нас недостаточно сведений о будущем, чтобы иметь возможность сказать, что возможность X будет добавлена за время или в версии Y. Как и в случае с любым программным обеспечением, приоритеты, расписания выпусков и доступные ресурсы могут измениться в любой момент.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-116">All that said, we don’t have enough information about the future to be able to say that feature X will be resolved by time/release Y. As in all software projects, priorities, release schedules, and available resources can change at any point.</span></span>

## <a name="release-planning-process"></a><span data-ttu-id="3b1f5-117">Процесс планирования выпусков</span><span class="sxs-lookup"><span data-stu-id="3b1f5-117">Release planning process</span></span>

<span data-ttu-id="3b1f5-118">Мы часто получаем вопросы о том, как мы выбираем возможности, которые будут добавлены в конкретный выпуск.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-118">We often get questions about how we choose specific features to go into a particular release.</span></span> <span data-ttu-id="3b1f5-119">Наш список невыполненной работы не становится автоматически планом выпусков.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-119">Our backlog certainly does not automatically translate into release plans.</span></span> <span data-ttu-id="3b1f5-120">Наличие возможности в EF6 также не означает автоматически, что она должна быть реализована в EF Core.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-120">The presence of a feature in EF6 also does not automatically mean that the feature needs to be implemented in EF Core.</span></span>

<span data-ttu-id="3b1f5-121">Сложно подробно описать весь процесс планирования выпуска, отчасти от того,что большую часть занимает обсуждение конкретных функций, возможностей и приоритетов, отчасти от того, что сам процесс обычно эволюционирует от выпуска к выпуску.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-121">It is difficult to detail here the whole process we follow to plan a release, partly because a lot of it is discussing the specific features, opportunities and priorities, and partly because the process itself usually evolves with every release.</span></span> <span data-ttu-id="3b1f5-122">Тем не менее можно относительно легко привести список наиболее распространенных вопросов, на которые мы пытаемся найти ответ при принятии решения о том, над чем мы будем работать на следующем этапе:</span><span class="sxs-lookup"><span data-stu-id="3b1f5-122">However, it is relatively easy to summarize the common questions we try to answer when deciding what to work on next:</span></span>

1. <span data-ttu-id="3b1f5-123">**Сколько разработчиков, по нашему мнению, будет использовать новую возможность, насколько она улучшит их приложения и облегчит процесс разработки?**</span><span class="sxs-lookup"><span data-stu-id="3b1f5-123">**How many developers we think will use the feature and how much better will it make their applications/experience?**</span></span> <span data-ttu-id="3b1f5-124">Для этого мы собираем отзывы из множества источников, комментарии и голосования за проблемы — один из таких источников.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-124">We aggregate feedback from many sources into this — Comments and votes on issues is one of those sources.</span></span>

2. <span data-ttu-id="3b1f5-125">**Какие существуют обходные пути для использования этой возможности, пока мы ее не реализовали?**</span><span class="sxs-lookup"><span data-stu-id="3b1f5-125">**What are the workarounds people can use if we don’t implement this feature yet?**</span></span> <span data-ttu-id="3b1f5-126">Например, многие разработчики используют сопоставление соединяемой таблицы для обхода отсутствия встроенной поддержки связи многие ко многим.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-126">For example, many developers are able to map a join table in order to work around lack of native many-to-many support.</span></span> <span data-ttu-id="3b1f5-127">Очевидно, что не все разработчики могут использовать эту возможность, но многие сумеют, и это является фактором, который влияет на принятие решения.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-127">Obviously, not all developers can do this, but many can, and this is a factor which counts.</span></span>

3. <span data-ttu-id="3b1f5-128">**Будет ли реализация этой возможности способствовать развитию EF Core, то есть приблизит ли это реализацию других возможностей?**</span><span class="sxs-lookup"><span data-stu-id="3b1f5-128">**Does implementing this feature evolve the architecture of EF Core such that it moves us closer to implementing other features?**</span></span> <span data-ttu-id="3b1f5-129">Как правило, мы отдаем предпочтение возможностям, выступающим в качестве строительных блоков для других функций. Например, разделение таблицы для собственных типов продвигает нас в реализации поддержки подхода TPT (одна таблица на тип).</span><span class="sxs-lookup"><span data-stu-id="3b1f5-129">We tend to favor features that act as building blocks for other features—for example, the table splitting that was done for owned types helps us move towards TPT support.</span></span>

4. <span data-ttu-id="3b1f5-130">**Является ли возможность точкой расширяемости?**</span><span class="sxs-lookup"><span data-stu-id="3b1f5-130">**Is the feature an extensibility point?**</span></span> <span data-ttu-id="3b1f5-131">Как правило, мы отдаем предпочтение точкам расширяемости, так как они позволяют разработчикам легко реализовывать собственные алгоритмы и использовать некоторые из нереализованных возможностей.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-131">We tend to favor extensibility points because they enable developers to more easily hook in their own behaviors and get some of the missing functionality that way.</span></span> <span data-ttu-id="3b1f5-132">Мы планируем реализовать кое-что из этого в начале работы над отложенной загрузкой.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-132">We’re planning to do some of this as a start to the lazy loading work.</span></span>

5. <span data-ttu-id="3b1f5-133">**Каков синергетический эффект от использования этой возможности в сочетании с другими продуктами?**</span><span class="sxs-lookup"><span data-stu-id="3b1f5-133">**What is the synergy of the feature when used in combination with other products?**</span></span> <span data-ttu-id="3b1f5-134">Как правило, мы отдаем предпочтение возможностям, позволяющим использовать EF Core с другими продуктами или значительно улучшить процесс использования других продуктов, таких как .NET Core, последняя версия Visual Studio, Microsoft Azure и т. д.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-134">We tend to favor features that allow EF Core to be used with other products or to significantly improve the experience of using other products, such as .NET Core, the latest version of Visual Studio, Microsoft Azure, etc.</span></span>

6. <span data-ttu-id="3b1f5-135">**Какова квалификация людей, доступных для работы над этой возможностью, и как лучше всего распорядиться этими ресурсами?**</span><span class="sxs-lookup"><span data-stu-id="3b1f5-135">**What are the capabilities of the people available to work on a feature, and how to best leverage these resources?**</span></span> <span data-ttu-id="3b1f5-136">Все члены команды EF и даже участники сообщества обладают разным уровнем опыта в различных областях, и при планировании мы должны это учитывать.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-136">Each member of the EF team and even our community contributors have different levels of experience in different areas and we have to plan accordingly.</span></span> <span data-ttu-id="3b1f5-137">Даже если бы мы захотели бросить все силы на работу над конкретной возможностью, такой как преобразование оператора GroupBy или связи многие ко многим, это было бы непрактично.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-137">Even if we wanted to have “all hands on deck” to work on a specific feature like GroupBy translations, or many-to-many, that wouldn’t be practical.</span></span>

<span data-ttu-id="3b1f5-138">Как упоминалось ранее, этот процесс развивается от выпуска к выпуску, и в будущем мы хотим добавить больше возможностей членам сообщества разработчиков для участия в разработке плана выпуска, например, облегчая рецензирование предложенных проектов возможностей и самого плана выпуска.</span><span class="sxs-lookup"><span data-stu-id="3b1f5-138">As mentioned before, this process evolves on every release, and in the future we would like to add more opportunities for members of the developer community to provide inputs into release plans, e.g. by making it easier to review proposed drafts of the features and of the release plan itself.</span></span>