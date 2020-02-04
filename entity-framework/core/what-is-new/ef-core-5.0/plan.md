---
title: Планирование для Entity Framework Core 5.0
author: ajcvickers
ms.date: 01/14/2020
uid: core/what-is-new/ef-core-5.0/plan.md
ms.openlocfilehash: 0472841fdcd105ec8ea38db062c6768510b8735d
ms.sourcegitcommit: f2a38c086291699422d8b28a72d9611d1b24ad0d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76125358"
---
# <a name="plan-for-entity-framework-core-50"></a><span data-ttu-id="7f919-102">Планирование для Entity Framework Core 5.0</span><span class="sxs-lookup"><span data-stu-id="7f919-102">Plan for Entity Framework Core 5.0</span></span>

<span data-ttu-id="7f919-103">Как было описано в [процессе планирования](../release-planning.md), мы собрали сведения от заинтересованных лиц в предварительный план для выпуска EF Core 5.0.</span><span class="sxs-lookup"><span data-stu-id="7f919-103">As described in the [planning process](../release-planning.md), we have gathered input from stakeholders into a tentative plan for the EF Core 5.0 release.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="7f919-104">Этот план отражает все еще продолжающиеся работы.</span><span class="sxs-lookup"><span data-stu-id="7f919-104">This plan is still a work-in-progress.</span></span> <span data-ttu-id="7f919-105">Ничего из приведенного здесь не является обязательством.</span><span class="sxs-lookup"><span data-stu-id="7f919-105">Nothing here is a commitment.</span></span> <span data-ttu-id="7f919-106">Этот план является отправной точкой и будет расширяться по мере обучения.</span><span class="sxs-lookup"><span data-stu-id="7f919-106">This plan is a starting point that will evolve as we learn more.</span></span> <span data-ttu-id="7f919-107">Могут быть включены некоторые вещи, пока не запланированные для версии 5.0,</span><span class="sxs-lookup"><span data-stu-id="7f919-107">Some things not currently planned for 5.0 may get pulled in.</span></span> <span data-ttu-id="7f919-108">и исключены некоторые вещи, уже запланированные для этой версии.</span><span class="sxs-lookup"><span data-stu-id="7f919-108">Some things currently planned for 5.0 may get punted out.</span></span>

### <a name="version-number-and-release-date"></a><span data-ttu-id="7f919-109">Номер версии и дата выпуска.</span><span class="sxs-lookup"><span data-stu-id="7f919-109">Version number and release date.</span></span>

<span data-ttu-id="7f919-110">Сейчас выпуск EF Core 5.0 запланирован на [то же самое время, что и.NET 5.0](https://devblogs.microsoft.com/dotnet/introducing-net-5/).</span><span class="sxs-lookup"><span data-stu-id="7f919-110">EF Core 5.0 is currently scheduled for release at [the same time as .NET 5.0](https://devblogs.microsoft.com/dotnet/introducing-net-5/).</span></span> <span data-ttu-id="7f919-111">Версия "5.0" была выбрана для согласования с .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="7f919-111">The version "5.0" was chosen to align with .NET 5.0.</span></span>

### <a name="supported-platforms"></a><span data-ttu-id="7f919-112">Поддерживаемые платформы</span><span class="sxs-lookup"><span data-stu-id="7f919-112">Supported platforms</span></span>

<span data-ttu-id="7f919-113">Планируется, что EF Core 5.0 можно будет запускать на любой платформе .NET 5.0 на основе [конвергенции этих платформ в .NET Core](https://devblogs.microsoft.com/dotnet/introducing-net-5/).</span><span class="sxs-lookup"><span data-stu-id="7f919-113">EF Core 5.0 is planned to run on any .NET 5.0 platform based on the [convergence of these platforms to .NET Core](https://devblogs.microsoft.com/dotnet/introducing-net-5/).</span></span> <span data-ttu-id="7f919-114">Что это означает с точки зрения .NET Standard и фактически используемого TFM, еще предстоит установить.</span><span class="sxs-lookup"><span data-stu-id="7f919-114">What this means in terms of .NET Standard and the actual TFM used is still TBD.</span></span>

<span data-ttu-id="7f919-115">EF Core 5.0 не будет работать в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f919-115">EF Core 5.0 will not run on .NET Framework.</span></span>

### <a name="breaking-changes"></a><span data-ttu-id="7f919-116">Критические изменения</span><span class="sxs-lookup"><span data-stu-id="7f919-116">Breaking changes</span></span>

<span data-ttu-id="7f919-117">EF Core 5.0 будет содержать некоторые критические изменения, но они будут гораздо менее серьезными, чем в случае с EF Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="7f919-117">EF Core 5.0 will contain some breaking changes, but these will be much less severe than was the case for EF Core 3.0.</span></span> <span data-ttu-id="7f919-118">Наша цель состоит в том, чтобы позволить подавляющему большинству приложений осуществлять обновление без нарушения работы.</span><span class="sxs-lookup"><span data-stu-id="7f919-118">Our goal is to allow the vast majority of applications to update without breaking.</span></span>

<span data-ttu-id="7f919-119">Ожидаются некоторые критические изменения для поставщиков баз данных, особенно связанные с поддержкой метода "одна таблица на тип".</span><span class="sxs-lookup"><span data-stu-id="7f919-119">It is expected that there will be some breaking changes for database providers, especially around TPT support.</span></span> <span data-ttu-id="7f919-120">Однако мы ожидаем, что обновление поставщика для версии 5.0 потребует меньше работы, чем при обновлении для версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="7f919-120">However, we expect the work to update a provider for 5.0 will be less than was required to update for 3.0.</span></span>

## <a name="themes"></a><span data-ttu-id="7f919-121">Темы</span><span class="sxs-lookup"><span data-stu-id="7f919-121">Themes</span></span>

<span data-ttu-id="7f919-122">Мы определили несколько основных областей или тем, которые сформируют основу для крупномасштабных инвестиций в EF Core 5.0.</span><span class="sxs-lookup"><span data-stu-id="7f919-122">We have extracted a few major areas or themes which will form the basis for the large investments in EF Core 5.0.</span></span>

## <a name="many-to-many-navigation-properties-aka-skip-navigations"></a><span data-ttu-id="7f919-123">Свойства навигации "многие ко многим" (или "навигации с пропуском")</span><span class="sxs-lookup"><span data-stu-id="7f919-123">Many-to-many navigation properties (a.k.a "skip navigations")</span></span>

<span data-ttu-id="7f919-124">Ведущие разработчики: @smitpatel и @AndriySvyryd</span><span class="sxs-lookup"><span data-stu-id="7f919-124">Lead developers: @smitpatel and @AndriySvyryd</span></span>

<span data-ttu-id="7f919-125">Отслеживание с помощью [#19003](https://github.com/aspnet/EntityFrameworkCore/issues/19003)</span><span class="sxs-lookup"><span data-stu-id="7f919-125">Tracked by [#19003](https://github.com/aspnet/EntityFrameworkCore/issues/19003)</span></span>

<span data-ttu-id="7f919-126">Размер футболки: L</span><span class="sxs-lookup"><span data-stu-id="7f919-126">T-shirt size: L</span></span>

<span data-ttu-id="7f919-127">Состояние: ведутся работы</span><span class="sxs-lookup"><span data-stu-id="7f919-127">Status: In-progress</span></span>

<span data-ttu-id="7f919-128">Функция "многие ко многим" является наиболее востребованной (около 407 голосов) в журнале невыполненной работы GitHub.</span><span class="sxs-lookup"><span data-stu-id="7f919-128">Many-to-many is the most requested feature (~407 votes) on the GitHub backlog.</span></span> <span data-ttu-id="7f919-129">Поддержку связей "многие ко многим" можно разбить на три основные области:</span><span class="sxs-lookup"><span data-stu-id="7f919-129">Support for many-to-many relationships can be broken down into three major areas:</span></span>

* <span data-ttu-id="7f919-130">Свойства навигации с пропуском.</span><span class="sxs-lookup"><span data-stu-id="7f919-130">Skip navigation properties.</span></span> <span data-ttu-id="7f919-131">Они позволяют использовать модель для запросов и т. п. без ссылки на базовую сущность таблицы соединений.</span><span class="sxs-lookup"><span data-stu-id="7f919-131">These allow the model to be used for queries, etc. without reference to the underlying join table entity.</span></span>
* <span data-ttu-id="7f919-132">Типы сущностей контейнера свойств.</span><span class="sxs-lookup"><span data-stu-id="7f919-132">Property-bag entity types.</span></span> <span data-ttu-id="7f919-133">Они позволяют использовать стандартный тип CLR (например, `Dictionary`) для экземпляров сущностей таким образом, чтобы для каждого типа сущности не требовался явный тип CLR.</span><span class="sxs-lookup"><span data-stu-id="7f919-133">These allow a standard CLR type (e.g. `Dictionary`) to be used for entity instances such that an explicit CLR type is not needed for each entity type.</span></span>
* <span data-ttu-id="7f919-134">Средства для простоты настройки связей "многие ко многим".</span><span class="sxs-lookup"><span data-stu-id="7f919-134">Sugar for easy configuration of many-to-many relationships.</span></span>

<span data-ttu-id="7f919-135">Мы считаем, что наиболее существенным препятствием для тех, кому требуется поддержка типа "многие ко многим", заключается в невозможности использовать "естественные" связи, не ссылаясь на таблицу соединений, в бизнес-логике, такой как запросы.</span><span class="sxs-lookup"><span data-stu-id="7f919-135">We believe that the most significant blocker for those wanting many-to-many support is not being able to use the "natural" relationships, without referring to the join table, in business logic such as queries.</span></span> <span data-ttu-id="7f919-136">Тип сущности таблицы соединений может по-прежнему существовать, но не должен мешать бизнес-логике.</span><span class="sxs-lookup"><span data-stu-id="7f919-136">The join table entity type may still exist, but it should not get in the way of business logic.</span></span> <span data-ttu-id="7f919-137">Именно поэтому мы решили взяться за свойства навигации с пропуском для версии 5.0.</span><span class="sxs-lookup"><span data-stu-id="7f919-137">This is why we have chosen to tackle skip navigation properties for 5.0.</span></span>

<span data-ttu-id="7f919-138">Сейчас другие части функции "многие ко многим" относятся к сверхплановой цели для EF Core 5.0.</span><span class="sxs-lookup"><span data-stu-id="7f919-138">At this time the other parts of many-to-many are being pursued as a stretch goal for EF Core 5.0.</span></span> <span data-ttu-id="7f919-139">Это означает, что сейчас они отсутствуют в плане для версии 5.0, но, если все пойдет хорошо, мы надеемся включить их туда.</span><span class="sxs-lookup"><span data-stu-id="7f919-139">This means they are not currently in the plan for 5.0, but if things go well we hope to pull them in.</span></span>

## <a name="table-per-type-tpt-inheritance-mapping"></a><span data-ttu-id="7f919-140">Сопоставление наследования "одна таблица на тип"</span><span class="sxs-lookup"><span data-stu-id="7f919-140">Table-per-type (TPT) inheritance mapping</span></span>

<span data-ttu-id="7f919-141">Ведущий разработчик: @AndriySvyryd</span><span class="sxs-lookup"><span data-stu-id="7f919-141">Lead developer: @AndriySvyryd</span></span>

<span data-ttu-id="7f919-142">Отслеживание с помощью [#2266](https://github.com/aspnet/EntityFrameworkCore/issues/2266)</span><span class="sxs-lookup"><span data-stu-id="7f919-142">Tracked by [#2266](https://github.com/aspnet/EntityFrameworkCore/issues/2266)</span></span>

<span data-ttu-id="7f919-143">Размер футболки: XL</span><span class="sxs-lookup"><span data-stu-id="7f919-143">T-shirt size: XL</span></span>

<span data-ttu-id="7f919-144">Состояние: работа не начата</span><span class="sxs-lookup"><span data-stu-id="7f919-144">Status: Not started</span></span>

<span data-ttu-id="7f919-145">Мы работаем над методом "одна таблица на тип", так как это очень востребованная функция (около 254 голосов; третье место) и для нее требуются некоторые низкоуровневые изменения, которые, по нашему мнению, согласуются с основополагающим характером общего плана по .NET 5.</span><span class="sxs-lookup"><span data-stu-id="7f919-145">We're doing TPT because it is both a highly requested feature (~254 votes; 3rd overall) and because it requires some low-level changes that we feel are appropriate for the foundational nature of the overall .NET 5 plan.</span></span> <span data-ttu-id="7f919-146">Мы предполагаем, что это приведет к критическим изменениям для поставщиков баз данных, хотя они должны быть гораздо менее серьезными, чем для версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="7f919-146">We expect this to result in breaking changes for database providers, although these should be much less severe than the changes required for 3.0.</span></span>

## <a name="filtered-include"></a><span data-ttu-id="7f919-147">Включение с фильтрацией</span><span class="sxs-lookup"><span data-stu-id="7f919-147">Filtered Include</span></span>

<span data-ttu-id="7f919-148">Ведущий разработчик: @maumar</span><span class="sxs-lookup"><span data-stu-id="7f919-148">Lead developer: @maumar</span></span>

<span data-ttu-id="7f919-149">Отслеживание с помощью [#1833](https://github.com/aspnet/EntityFrameworkCore/issues/1833)</span><span class="sxs-lookup"><span data-stu-id="7f919-149">Tracked by [#1833](https://github.com/aspnet/EntityFrameworkCore/issues/1833)</span></span>

<span data-ttu-id="7f919-150">Размер футболки: M</span><span class="sxs-lookup"><span data-stu-id="7f919-150">T-shirt size: M</span></span>

<span data-ttu-id="7f919-151">Состояние: работа не начата</span><span class="sxs-lookup"><span data-stu-id="7f919-151">Status: Not started</span></span>

<span data-ttu-id="7f919-152">Включение с фильтрацией — это очень востребованная функция (около 317 голосов; второе место), которая потребует не слишком много работы и, по нашему мнению, позволит реализовать или упростить многие сценарии, в которых сейчас требуются фильтры уровня модели или более сложные запросы.</span><span class="sxs-lookup"><span data-stu-id="7f919-152">Filtered Include is a highly-requested feature (~317 votes; 2nd overall) that isn't a huge amount of work, and that we believe will unblock or make easier many scenarios that currently require model-level filters or more complex queries.</span></span>

## <a name="rationalize-totable-toquery-toview-fromsql-etc"></a><span data-ttu-id="7f919-153">Оптимизация ToTable, ToQuery, ToView, FromSql и т. п.</span><span class="sxs-lookup"><span data-stu-id="7f919-153">Rationalize ToTable, ToQuery, ToView, FromSql, etc.</span></span>

<span data-ttu-id="7f919-154">Ведущие разработчики: @maumar и @smitpatel</span><span class="sxs-lookup"><span data-stu-id="7f919-154">Lead developers: @maumar and @smitpatel</span></span>

<span data-ttu-id="7f919-155">Отслеживание с помощью [#17270](https://github.com/aspnet/EntityFrameworkCore/issues/17270)</span><span class="sxs-lookup"><span data-stu-id="7f919-155">Tracked by [#17270](https://github.com/aspnet/EntityFrameworkCore/issues/17270)</span></span>

<span data-ttu-id="7f919-156">Размер футболки: L</span><span class="sxs-lookup"><span data-stu-id="7f919-156">T-shirt size: L</span></span>

<span data-ttu-id="7f919-157">Состояние: работа не начата</span><span class="sxs-lookup"><span data-stu-id="7f919-157">Status: Not started</span></span>

<span data-ttu-id="7f919-158">В предыдущих выпусках мы уже проделали определенную работу для поддержки необработанного SQL-кода, бесключевых типов и связанных с ними аспектов.</span><span class="sxs-lookup"><span data-stu-id="7f919-158">We have made progress in previous releases towards supporting raw SQL, keyless types, and related areas.</span></span> <span data-ttu-id="7f919-159">Однако при попытке обеспечить работу этих функций как единого целого выявляются недочеты и несоответствия.</span><span class="sxs-lookup"><span data-stu-id="7f919-159">However, there are both gaps and inconsistencies in the way everything works together as a whole.</span></span> <span data-ttu-id="7f919-160">Версия 5.0 должна устранить эти проблемы и обеспечить удобное определение, перенос и использование различных типов сущностей и связанных с ними запросов и артефактов баз данных.</span><span class="sxs-lookup"><span data-stu-id="7f919-160">The goal for 5.0 is to fix these and create a good experience for defining, migrating, and using different types of entities and their associated queries and database artifacts.</span></span> <span data-ttu-id="7f919-161">Это также может потребовать внесения изменений в скомпилированный API запросов.</span><span class="sxs-lookup"><span data-stu-id="7f919-161">This may also involve updates to the compiled query API.</span></span>

<span data-ttu-id="7f919-162">Обратите внимание, что этот пункт может привести к некоторым критическим изменениям на уровне приложения, так как некоторые функциональные возможности, которыми мы сейчас располагаем, допускают слишком вольное обращение с ними, что может быстро привести к сбою.</span><span class="sxs-lookup"><span data-stu-id="7f919-162">Note that this item may result in some application-level breaking changes since some of the functionality we currently have is too permissive such that it can quickly lead people into pits of failure.</span></span> <span data-ttu-id="7f919-163">Скорее всего, мы заблокируем некоторые из этих функций и порекомендуем, чем их заменить.</span><span class="sxs-lookup"><span data-stu-id="7f919-163">We will likely end up blocking some of this functionality together with guidance on what to do instead.</span></span>

## <a name="general-query-enhancements"></a><span data-ttu-id="7f919-164">Общие усовершенствования запросов</span><span class="sxs-lookup"><span data-stu-id="7f919-164">General query enhancements</span></span>

<span data-ttu-id="7f919-165">Ведущие разработчики: @smitpatel и @maumar</span><span class="sxs-lookup"><span data-stu-id="7f919-165">Lead developers: @smitpatel and @maumar</span></span>

<span data-ttu-id="7f919-166">Отслеживание с помощью [вопроса, отмеченного `area-query` в вехе 5.0](https://github.com/dotnet/efcore/issues?utf8=%E2%9C%93&q=is%3Aissue+label%3Aarea-query+milestone%3A5.0.0+)</span><span class="sxs-lookup"><span data-stu-id="7f919-166">Tracked by [issues labeled with `area-query` in the 5.0 milestone](https://github.com/dotnet/efcore/issues?utf8=%E2%9C%93&q=is%3Aissue+label%3Aarea-query+milestone%3A5.0.0+)</span></span>

<span data-ttu-id="7f919-167">Размер футболки: XL</span><span class="sxs-lookup"><span data-stu-id="7f919-167">T-shirt size: XL</span></span>

<span data-ttu-id="7f919-168">Состояние: ведутся работы</span><span class="sxs-lookup"><span data-stu-id="7f919-168">Status: In-progress</span></span>

<span data-ttu-id="7f919-169">Код преобразования запроса для EF Core 3.0 был в значительной степени переписан.</span><span class="sxs-lookup"><span data-stu-id="7f919-169">The query translation code was extensively rewritten for EF Core 3.0.</span></span> <span data-ttu-id="7f919-170">Благодаря этому в общем случае код запроса находится в значительно более надежном состоянии.</span><span class="sxs-lookup"><span data-stu-id="7f919-170">The query code is generally in a much more robust state because of this.</span></span> <span data-ttu-id="7f919-171">Для версии 5.0 мы не планируем вносить существенные изменения в запросы, за исключением тех, которые необходимы для поддержки метода "одна таблица на тип" и свойств навигации с пропуском.</span><span class="sxs-lookup"><span data-stu-id="7f919-171">For 5.0 we aren't planning on making major query changes, outside those needed to support TPT and skip navigation properties.</span></span> <span data-ttu-id="7f919-172">Однако по-прежнему требуется значительная работа, чтобы устранить технический долг, оставшийся после масштабного изменения версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="7f919-172">However, there is still significant work needed to fix some technical debt left over from the 3.0 overhaul.</span></span> <span data-ttu-id="7f919-173">Мы также планируем исправить многие ошибки и внести небольшие улучшения для дальнейшего улучшения общего процесса работы с запросами.</span><span class="sxs-lookup"><span data-stu-id="7f919-173">We also plan to fix many bugs and implement small enhancements to further improve the overall query experience.</span></span>

## <a name="migrations-and-deployment-experience"></a><span data-ttu-id="7f919-174">Процедура миграция и развертывания</span><span class="sxs-lookup"><span data-stu-id="7f919-174">Migrations and deployment experience</span></span>

<span data-ttu-id="7f919-175">Ведущие разработчики: @bricelam</span><span class="sxs-lookup"><span data-stu-id="7f919-175">Lead developers: @bricelam</span></span>

<span data-ttu-id="7f919-176">Отслеживание с помощью [#19587](https://github.com/dotnet/efcore/issues/19587)</span><span class="sxs-lookup"><span data-stu-id="7f919-176">Tracked by [#19587](https://github.com/dotnet/efcore/issues/19587)</span></span>

<span data-ttu-id="7f919-177">Размер футболки: L</span><span class="sxs-lookup"><span data-stu-id="7f919-177">T-shirt size: L</span></span>

<span data-ttu-id="7f919-178">Состояние: ведутся работы</span><span class="sxs-lookup"><span data-stu-id="7f919-178">Status: In-progress</span></span>

<span data-ttu-id="7f919-179">Сейчас многие разработчики переносят свои базы данных во время запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="7f919-179">Currently, many developers migrate their databases at application startup time.</span></span> <span data-ttu-id="7f919-180">Это удобно, но не рекомендовано по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="7f919-180">This is easy but is not recommended because:</span></span>

* <span data-ttu-id="7f919-181">Несколько потоков/процессов/серверов могут одновременно попытаться перенести базу данных.</span><span class="sxs-lookup"><span data-stu-id="7f919-181">Multiple threads/processes/servers may attempt to migrate the database concurrently</span></span>
* <span data-ttu-id="7f919-182">При этом приложения могут попытаться перейти в несогласованное состояние.</span><span class="sxs-lookup"><span data-stu-id="7f919-182">Applications may try to access inconsistent state while this is happening</span></span>
* <span data-ttu-id="7f919-183">В общем случае разрешения базы данных на изменение схемы не должны предоставляться для выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="7f919-183">Usually the database permissions to modify the schema should not be granted for application execution</span></span>
* <span data-ttu-id="7f919-184">Возврат к исходному состоянию в случае сбоя затруднен.</span><span class="sxs-lookup"><span data-stu-id="7f919-184">Its hard to revert back to a clean state if something goes wrong</span></span>

<span data-ttu-id="7f919-185">Мы хотим обеспечить улучшить эту процедуру, чтобы она позволяла легко перенести базу данных во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="7f919-185">We want to deliver a better experience here that allows an easy way to migrate the database at deployment time.</span></span> <span data-ttu-id="7f919-186">Предъявляются следующие требования:</span><span class="sxs-lookup"><span data-stu-id="7f919-186">This should:</span></span>

* <span data-ttu-id="7f919-187">Работа в Linux, Mac и Windows.</span><span class="sxs-lookup"><span data-stu-id="7f919-187">Work on Linux, Mac, and Windows</span></span>
* <span data-ttu-id="7f919-188">Хорошая совместимость с командной строкой.</span><span class="sxs-lookup"><span data-stu-id="7f919-188">Be a good experience on the command line</span></span>
* <span data-ttu-id="7f919-189">Поддержка сценариев с контейнерами.</span><span class="sxs-lookup"><span data-stu-id="7f919-189">Support scenarios with containers</span></span>
* <span data-ttu-id="7f919-190">Работа с средствами и потоками развертывания, часто применяемыми на практике.</span><span class="sxs-lookup"><span data-stu-id="7f919-190">Work with commonly used real-world deployment tools/flows</span></span>
* <span data-ttu-id="7f919-191">Интеграция по меньшей мере с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7f919-191">Integrate into at least Visual Studio</span></span>

<span data-ttu-id="7f919-192">Результат, скорее всего, будет представлять собой множество небольших улучшений в EF Core (например, улучшенная миграция в SQLite), а также руководства и долгосрочное сотрудничество с другими группами для улучшения комплексных возможностей, выходящих за пределы EF.</span><span class="sxs-lookup"><span data-stu-id="7f919-192">The result is likely to be many small improvements in EF Core (for example, better Migrations on SQLite), together with guidance and longer-term collaborations with other teams to improve end-to-end experiences that go beyond just EF.</span></span>

## <a name="ef-core-platforms-experience"></a><span data-ttu-id="7f919-193">Возможности платформ EF Core</span><span class="sxs-lookup"><span data-stu-id="7f919-193">EF Core platforms experience</span></span> 

<span data-ttu-id="7f919-194">Ведущие разработчики: @roji и @bricelam</span><span class="sxs-lookup"><span data-stu-id="7f919-194">Lead developers: @roji and @bricelam</span></span>

<span data-ttu-id="7f919-195">Отслеживание с помощью [#19588](https://github.com/dotnet/efcore/issues/19588)</span><span class="sxs-lookup"><span data-stu-id="7f919-195">Tracked by [#19588](https://github.com/dotnet/efcore/issues/19588)</span></span>

<span data-ttu-id="7f919-196">Размер футболки: L</span><span class="sxs-lookup"><span data-stu-id="7f919-196">T-shirt size: L</span></span>

<span data-ttu-id="7f919-197">Состояние: работа не начата</span><span class="sxs-lookup"><span data-stu-id="7f919-197">Status: Not started</span></span>

<span data-ttu-id="7f919-198">У нас есть хорошее руководство по использованию EF Core в традиционных веб-приложениях, работающих по принципу MVC.</span><span class="sxs-lookup"><span data-stu-id="7f919-198">We have good guidance for using EF Core in traditional MVC-like web applications.</span></span> <span data-ttu-id="7f919-199">Рекомендации для других платформ и моделей приложений отсутствуют или устарели.</span><span class="sxs-lookup"><span data-stu-id="7f919-199">Guidance for other platforms and application models is either missing or out-of-date.</span></span> <span data-ttu-id="7f919-200">Для EF Core 5.0 мы планируем изучить, улучшить и задокументировать процесс использования EF Core со следующими компонентами:</span><span class="sxs-lookup"><span data-stu-id="7f919-200">For EF Core 5.0 we plan to investigate, improve, and document the experience of using EF Core with:</span></span>

* <span data-ttu-id="7f919-201">Blazor</span><span class="sxs-lookup"><span data-stu-id="7f919-201">Blazor</span></span>
* <span data-ttu-id="7f919-202">Xamarin, в том числе использование AOT или компоновщика</span><span class="sxs-lookup"><span data-stu-id="7f919-202">Xamarin, including using the AOT/linker story</span></span>
* <span data-ttu-id="7f919-203">WinForms/WPF/WinUI и, возможно, другие платформы пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="7f919-203">WinForms/WPF/WinUI and possibly other U.I.</span></span> <span data-ttu-id="7f919-204">Инфраструктуры</span><span class="sxs-lookup"><span data-stu-id="7f919-204">frameworks</span></span>

<span data-ttu-id="7f919-205">Результат, скорее всего, будет представлять собой множество небольших улучшений в EF Core, а также руководства и долгосрочное сотрудничество с другими группами для улучшения комплексных возможностей, выходящих за пределы EF.</span><span class="sxs-lookup"><span data-stu-id="7f919-205">This is likely to be many small improvements in EF Core, together with guidance and longer-term collaborations with other teams to improve end-to-end experiences that go beyond just EF.</span></span>

<span data-ttu-id="7f919-206">Ниже перечислены конкретные области, которые мы планируем рассмотреть:</span><span class="sxs-lookup"><span data-stu-id="7f919-206">Specific areas we plan to look at are:</span></span>

* <span data-ttu-id="7f919-207">Развертывание, включая интерфейс для использования средств EF, таких как миграции</span><span class="sxs-lookup"><span data-stu-id="7f919-207">Deployment, including the experience for using EF tooling such as for Migrations</span></span>
* <span data-ttu-id="7f919-208">Модели приложений, включая Xamarin и Blazor, и, возможно, другие</span><span class="sxs-lookup"><span data-stu-id="7f919-208">Application models, including Xamarin and Blazor, and probably others</span></span>
* <span data-ttu-id="7f919-209">Процедуры для SQLite, включая пространственное взаимодействие и перестроение таблиц</span><span class="sxs-lookup"><span data-stu-id="7f919-209">SQLite experiences, including the spatial experience and table rebuilds</span></span>
* <span data-ttu-id="7f919-210">Процедуры для AOT и компоновки</span><span class="sxs-lookup"><span data-stu-id="7f919-210">AOT and linking experiences</span></span>
* <span data-ttu-id="7f919-211">Интеграция диагностики, включая счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="7f919-211">Diagnostics integration, including perf counters</span></span>

## <a name="performance"></a><span data-ttu-id="7f919-212">Производительность</span><span class="sxs-lookup"><span data-stu-id="7f919-212">Performance</span></span>

<span data-ttu-id="7f919-213">Ведущий разработчик: @roji</span><span class="sxs-lookup"><span data-stu-id="7f919-213">Lead developer: @roji</span></span>

<span data-ttu-id="7f919-214">Отслеживание с помощью [вопроса, отмеченного `area-perf` в вехе 5.0](https://github.com/dotnet/efcore/issues?utf8=%E2%9C%93&q=is%3Aissue+label%3Aarea-perf+milestone%3A5.0.0+)</span><span class="sxs-lookup"><span data-stu-id="7f919-214">Tracked by [issues labeled with `area-perf` in the 5.0 milestone](https://github.com/dotnet/efcore/issues?utf8=%E2%9C%93&q=is%3Aissue+label%3Aarea-perf+milestone%3A5.0.0+)</span></span>

<span data-ttu-id="7f919-215">Размер футболки: L</span><span class="sxs-lookup"><span data-stu-id="7f919-215">T-shirt size: L</span></span>

<span data-ttu-id="7f919-216">Состояние: ведутся работы</span><span class="sxs-lookup"><span data-stu-id="7f919-216">Status: In-progress</span></span>

<span data-ttu-id="7f919-217">Для EF Core мы планируем улучшить набор тестов производительность и внести целевые улучшения производительности для среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="7f919-217">For EF Core we plan to improve our suite of performance benchmarks and make directed performance improvements to the runtime.</span></span> <span data-ttu-id="7f919-218">Кроме того, мы планируем завершить новый API пакетной обработки ADO.NET, который находился на этапе прототипа со времени цикла выпуска версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="7f919-218">In addition, we plan to complete the new ADO.NET batching API which was prototyped during the 3.0 release cycle.</span></span> <span data-ttu-id="7f919-219">Кроме того, на уровне ADO.NET мы планируем дополнительно улучшить производительность для поставщика Npgsql.</span><span class="sxs-lookup"><span data-stu-id="7f919-219">Also at the ADO.NET layer, we plan additional performance improvements to the Npgsql provider.</span></span>

<span data-ttu-id="7f919-220">В рамках этой задачи мы также планируем добавить счетчики производительности ADO.NET/EF Core и другие средства диагностики.</span><span class="sxs-lookup"><span data-stu-id="7f919-220">As part of this work we also plan to add ADO.NET/EF Core performance counters and other diagnostics as appropriate.</span></span>

## <a name="architecturalcontributor-documentation"></a><span data-ttu-id="7f919-221">Документация по архитектуре и участникам</span><span class="sxs-lookup"><span data-stu-id="7f919-221">Architectural/contributor documentation</span></span>

<span data-ttu-id="7f919-222">Ведущий документатор: @ajcvickers</span><span class="sxs-lookup"><span data-stu-id="7f919-222">Lead documenter: @ajcvickers</span></span>

<span data-ttu-id="7f919-223">Отслеживание с помощью [#1920](https://github.com/aspnet/EntityFramework.Docs/issues/1920)</span><span class="sxs-lookup"><span data-stu-id="7f919-223">Tracked by [#1920](https://github.com/aspnet/EntityFramework.Docs/issues/1920)</span></span>

<span data-ttu-id="7f919-224">Размер футболки: L</span><span class="sxs-lookup"><span data-stu-id="7f919-224">T-shirt size: L</span></span>

<span data-ttu-id="7f919-225">Состояние: работа не начата</span><span class="sxs-lookup"><span data-stu-id="7f919-225">Status: Not started</span></span>

<span data-ttu-id="7f919-226">Идея заключается в том, чтобы упростить понимание того, что происходит внутри EF Core.</span><span class="sxs-lookup"><span data-stu-id="7f919-226">The idea here is to make it easier to understand what is going on in the internals of EF Core.</span></span> <span data-ttu-id="7f919-227">Это может быть полезно любому пользователю EF Core, однако основная мотивация заключается в том, чтобы упростить выполнение внешними пользователями следующих операций:</span><span class="sxs-lookup"><span data-stu-id="7f919-227">This can be useful to anyone using EF Core, but the primary motivation is to make it easier for external people to:</span></span>

* <span data-ttu-id="7f919-228">Участие в разработке кода EF Core</span><span class="sxs-lookup"><span data-stu-id="7f919-228">Contribute to the EF Core code</span></span>
* <span data-ttu-id="7f919-229">Создание поставщиков баз данных</span><span class="sxs-lookup"><span data-stu-id="7f919-229">Create database providers</span></span>
* <span data-ttu-id="7f919-230">Создание других расширений</span><span class="sxs-lookup"><span data-stu-id="7f919-230">Build other extensions</span></span>

## <a name="microsoftdatasqlite-documentation"></a><span data-ttu-id="7f919-231">Документация по Microsoft.Data.Sqlite</span><span class="sxs-lookup"><span data-stu-id="7f919-231">Microsoft.Data.Sqlite documentation</span></span>

<span data-ttu-id="7f919-232">Ведущий документатор: @bricelam</span><span class="sxs-lookup"><span data-stu-id="7f919-232">Lead documenter: @bricelam</span></span>

<span data-ttu-id="7f919-233">Отслеживание с помощью [#1675](https://github.com/aspnet/EntityFramework.Docs/issues/1675)</span><span class="sxs-lookup"><span data-stu-id="7f919-233">Tracked by [#1675](https://github.com/aspnet/EntityFramework.Docs/issues/1675)</span></span>

<span data-ttu-id="7f919-234">Размер футболки: M</span><span class="sxs-lookup"><span data-stu-id="7f919-234">T-shirt size: M</span></span>

<span data-ttu-id="7f919-235">Состояние: работа завершена.</span><span class="sxs-lookup"><span data-stu-id="7f919-235">Status: Completed.</span></span> <span data-ttu-id="7f919-236">Новая документация [доступна на веб-сайте документации Майкрософт](https://docs.microsoft.com/dotnet/standard/data/sqlite/?tabs=netcore-cli).</span><span class="sxs-lookup"><span data-stu-id="7f919-236">The new documentation is [live on the Microsoft docs site](https://docs.microsoft.com/dotnet/standard/data/sqlite/?tabs=netcore-cli).</span></span>

<span data-ttu-id="7f919-237">Группа EF также владеет поставщиком Microsoft.Data.Sqlite ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="7f919-237">The EF Team also owns the Microsoft.Data.Sqlite ADO.NET provider.</span></span> <span data-ttu-id="7f919-238">Мы планируем полностью задокументировать этот поставщик в рамках выпуска 5.0.</span><span class="sxs-lookup"><span data-stu-id="7f919-238">We plan to fully document this provider as part of the 5.0 release.</span></span>

## <a name="general-documentation"></a><span data-ttu-id="7f919-239">Общая документация</span><span class="sxs-lookup"><span data-stu-id="7f919-239">General documentation</span></span>

<span data-ttu-id="7f919-240">Ведущий документатор: @ajcvickers</span><span class="sxs-lookup"><span data-stu-id="7f919-240">Lead documenter: @ajcvickers</span></span>

<span data-ttu-id="7f919-241">Отслеживание с помощью [вопросов в репозитории документации в вехе 5.0](https://github.com/aspnet/EntityFramework.Docs/issues?utf8=%E2%9C%93&q=is%3Aissue+milestone%3A5.0.0+)</span><span class="sxs-lookup"><span data-stu-id="7f919-241">Tracked by [issues in the docs repo in the 5.0 milestone](https://github.com/aspnet/EntityFramework.Docs/issues?utf8=%E2%9C%93&q=is%3Aissue+milestone%3A5.0.0+)</span></span>

<span data-ttu-id="7f919-242">Размер футболки: L</span><span class="sxs-lookup"><span data-stu-id="7f919-242">T-shirt size: L</span></span>

<span data-ttu-id="7f919-243">Состояние: ведутся работы</span><span class="sxs-lookup"><span data-stu-id="7f919-243">Status: In-progress</span></span>

<span data-ttu-id="7f919-244">Мы уже приступили к обновлению документации для выпусков 3.0 и 3.1.</span><span class="sxs-lookup"><span data-stu-id="7f919-244">We are already in the process of updating documentation for the 3.0 and 3.1 releases.</span></span> <span data-ttu-id="7f919-245">Мы также работаем над следующими задачами:</span><span class="sxs-lookup"><span data-stu-id="7f919-245">We are also working on:</span></span>
  * <span data-ttu-id="7f919-246">Масштабная переработка документов по началу работы, чтобы сделать их более удобными и понятными</span><span class="sxs-lookup"><span data-stu-id="7f919-246">An overhaul of the getting started docs to make them more approachable/easier to follow</span></span>
  * <span data-ttu-id="7f919-247">Реорганизация документов для облегчения поиска и добавления перекрестных ссылок</span><span class="sxs-lookup"><span data-stu-id="7f919-247">Reorganization of docs to make things easier to find and to add cross-references</span></span>
  * <span data-ttu-id="7f919-248">Добавление дополнительных сведений и уточнений в существующие документы</span><span class="sxs-lookup"><span data-stu-id="7f919-248">Adding more details and clarifications to existing docs</span></span>
  * <span data-ttu-id="7f919-249">Обновление существующих и добавление новых примеров</span><span class="sxs-lookup"><span data-stu-id="7f919-249">Updating the samples and adding more examples</span></span>

## <a name="fixing-bugs"></a><span data-ttu-id="7f919-250">Исправление ошибок</span><span class="sxs-lookup"><span data-stu-id="7f919-250">Fixing bugs</span></span>

<span data-ttu-id="7f919-251">Отслеживание с помощью [вопроса, отмеченного `type-bug` в вехе 5.0](https://github.com/dotnet/efcore/issues?utf8=%E2%9C%93&q=is%3Aissue+milestone%3A5.0.0+label%3Atype-bug+)</span><span class="sxs-lookup"><span data-stu-id="7f919-251">Tracked by [issues labeled with `type-bug` in the 5.0 milestone](https://github.com/dotnet/efcore/issues?utf8=%E2%9C%93&q=is%3Aissue+milestone%3A5.0.0+label%3Atype-bug+)</span></span>

<span data-ttu-id="7f919-252">Разработчики: @roji, @maumar, @bricelam, @smitpatel, @AndriySvyryd, @ajcvickers</span><span class="sxs-lookup"><span data-stu-id="7f919-252">Developers: @roji, @maumar, @bricelam, @smitpatel, @AndriySvyryd, @ajcvickers</span></span>

<span data-ttu-id="7f919-253">Размер футболки: L</span><span class="sxs-lookup"><span data-stu-id="7f919-253">T-shirt size: L</span></span>

<span data-ttu-id="7f919-254">Состояние: ведутся работы</span><span class="sxs-lookup"><span data-stu-id="7f919-254">Status: In-progress</span></span>

<span data-ttu-id="7f919-255">На момент написания статьи у нас отобрано 135 ошибок для исправления в выпуске 5.0 (62 уже исправлены), однако они во многом пересекаются с разделом _Общие усовершенствования запросов_ выше.</span><span class="sxs-lookup"><span data-stu-id="7f919-255">At the time of writing, we have 135 bugs triaged to be fixed in the 5.0 release (with 62 already fixed), but there is significant overlap with the _General query enhancements_ section above.</span></span>

<span data-ttu-id="7f919-256">Скорость поступления (вопросы, превратившиеся в работу в вехе) в рамках выпуска 3.0 составила около 23 вопросов в месяц.</span><span class="sxs-lookup"><span data-stu-id="7f919-256">The incoming rate (issues that end up as work in a milestone) was about 23 issues per month over the course of the 3.0 release.</span></span> <span data-ttu-id="7f919-257">Не все из них потребуется исправить в версии 5.0.</span><span class="sxs-lookup"><span data-stu-id="7f919-257">Not all of these will need to be fixed in 5.0.</span></span> <span data-ttu-id="7f919-258">Ориентировочно в рамках работы над версией 5.0 мы планируем устранить 150 дополнительных проблем.</span><span class="sxs-lookup"><span data-stu-id="7f919-258">As a rough estimate we plan to fix an additional 150 issues in the 5.0 time frame.</span></span>

## <a name="small-enhancements"></a><span data-ttu-id="7f919-259">Небольшие усовершенствования</span><span class="sxs-lookup"><span data-stu-id="7f919-259">Small enhancements</span></span>

<span data-ttu-id="7f919-260">Отслеживание с помощью [вопроса, отмеченного `type-enhancement` в вехе 5.0](https://github.com/dotnet/efcore/issues?utf8=%E2%9C%93&q=is%3Aissue+milestone%3A5.0.0+label%3Atype-enhancement+)</span><span class="sxs-lookup"><span data-stu-id="7f919-260">Tracked by [issues labeled with `type-enhancement` in the 5.0 milestone](https://github.com/dotnet/efcore/issues?utf8=%E2%9C%93&q=is%3Aissue+milestone%3A5.0.0+label%3Atype-enhancement+)</span></span>

<span data-ttu-id="7f919-261">Разработчики: @roji, @maumar, @bricelam, @smitpatel, @AndriySvyryd, @ajcvickers</span><span class="sxs-lookup"><span data-stu-id="7f919-261">Developers: @roji, @maumar, @bricelam, @smitpatel, @AndriySvyryd, @ajcvickers</span></span>

<span data-ttu-id="7f919-262">Размер футболки: L</span><span class="sxs-lookup"><span data-stu-id="7f919-262">T-shirt size: L</span></span>

<span data-ttu-id="7f919-263">Состояние: ведутся работы</span><span class="sxs-lookup"><span data-stu-id="7f919-263">Status: In-progress</span></span>

<span data-ttu-id="7f919-264">В дополнение к более масштабным функциям, описанным выше, у нас также есть множество небольших усовершенствований, запланированных для версии 5.0, которые призваны исправить мелкие недочеты.</span><span class="sxs-lookup"><span data-stu-id="7f919-264">In addition to the bigger features outlined above, we also have many smaller improvements scheduled for 5.0 to fix "paper-cuts".</span></span> <span data-ttu-id="7f919-265">Обратите внимание, что многие из этих усовершенствований также входят в более общие темы, описанные выше.</span><span class="sxs-lookup"><span data-stu-id="7f919-265">Note that many of these enhancements are also covered by the more general themes outlined above.</span></span>

## <a name="below-the-line"></a><span data-ttu-id="7f919-266">Выход за пределы плана</span><span class="sxs-lookup"><span data-stu-id="7f919-266">Below-the-line</span></span>

<span data-ttu-id="7f919-267">Отслеживание с помощью [вопроса, отмеченного `consider-for-next-release`](https://github.com/aspnet/EntityFrameworkCore/issues?q=is%3Aopen+is%3Aissue+label%3Aconsider-for-next-release)</span><span class="sxs-lookup"><span data-stu-id="7f919-267">Tracked by [issues labeled with `consider-for-next-release`](https://github.com/aspnet/EntityFrameworkCore/issues?q=is%3Aopen+is%3Aissue+label%3Aconsider-for-next-release)</span></span>

<span data-ttu-id="7f919-268">Это исправления ошибок и усовершенствования, которые пока **не** запланированы для выпуска 5.0, но мы постараемся включить их в зависимости от того, как будет продвигаться описанная выше работа.</span><span class="sxs-lookup"><span data-stu-id="7f919-268">These are bug fixes and enhancements that are **not** currently scheduled for the 5.0 release, but we will look at as stretch goals depending on the progress made on the work above.</span></span>

<span data-ttu-id="7f919-269">Кроме того, при планировании мы всегда учитываем [вопросы, набравшие больше всего голосов](https://github.com/dotnet/efcore/issues?q=is%3Aissue+is%3Aopen+sort%3Areactions-%2B1-desc).</span><span class="sxs-lookup"><span data-stu-id="7f919-269">In addition, we always consider the [most voted issues](https://github.com/dotnet/efcore/issues?q=is%3Aissue+is%3Aopen+sort%3Areactions-%2B1-desc) when planning.</span></span> <span data-ttu-id="7f919-270">Исключение любой из подобных проблем из выпуска всегда дается нелегко, но нам нужен реалистичный план с учетом ресурсов, которыми мы располагаем.</span><span class="sxs-lookup"><span data-stu-id="7f919-270">Cutting any of these issues from a release is always painful, but we do need a realistic plan for the resources we have.</span></span>

## <a name="feedback"></a><span data-ttu-id="7f919-271">Отзывы</span><span class="sxs-lookup"><span data-stu-id="7f919-271">Feedback</span></span>

<span data-ttu-id="7f919-272">Нам важно ваше мнение о планировании.</span><span class="sxs-lookup"><span data-stu-id="7f919-272">Your feedback on planning is important.</span></span> <span data-ttu-id="7f919-273">Лучший способ указать важность проблемы — проголосовать за нее на GitHub.</span><span class="sxs-lookup"><span data-stu-id="7f919-273">The best way to indicate the importance of an issue is to vote (thumbs-up) for that issue on GitHub.</span></span> <span data-ttu-id="7f919-274">Эти данные будут учитываться в [процессе планирования](../release-planning.md) для следующего выпуска.</span><span class="sxs-lookup"><span data-stu-id="7f919-274">This data will then feed into the [planning process](../release-planning.md) for the next release.</span></span>