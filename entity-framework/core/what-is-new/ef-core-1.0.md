---
title: Новые возможности в Core EF 1.0 (EF Core)
author: divega
ms.date: 10/27/2016
ms.assetid: 20A25111-AEBE-4BC2-83A5-3F651952DF72
uid: core/what-is-new/ef-core-1.0
ms.openlocfilehash: 2cd2a54d75ed3f0caa8b674dfb56babcfcc13592
ms.sourcegitcommit: 9b562663679854c37c05fca13d93e180213fb4aa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "78413597"
---
# <a name="features-included-in-ef-core-10"></a><span data-ttu-id="7b53d-102">Возможности, добавленные в версии EF Core 1.0</span><span class="sxs-lookup"><span data-stu-id="7b53d-102">Features included in EF Core 1.0</span></span>

## <a name="platforms"></a><span data-ttu-id="7b53d-103">Платформы</span><span class="sxs-lookup"><span data-stu-id="7b53d-103">Platforms</span></span>

### <a name="net-framework-451"></a><span data-ttu-id="7b53d-104">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="7b53d-104">.NET Framework 4.5.1</span></span>

<span data-ttu-id="7b53d-105">Включает консоль, WPF, WinForms, ASP.NET 4 и многое другое.</span><span class="sxs-lookup"><span data-stu-id="7b53d-105">Includes Console, WPF, WinForms, ASP.NET 4, etc.</span></span>

### <a name="net-standard-13"></a><span data-ttu-id="7b53d-106">.NET Standard 1.3</span><span class="sxs-lookup"><span data-stu-id="7b53d-106">.NET Standard 1.3</span></span>

<span data-ttu-id="7b53d-107">Поддержка ASP.NET Core для .NET Framework и .NET Core в операционных системах Windows, OSX и Linux.</span><span class="sxs-lookup"><span data-stu-id="7b53d-107">Including ASP.NET Core targeting both .NET Framework and .NET Core on Windows, OSX, and Linux.</span></span>

## <a name="modelling"></a><span data-ttu-id="7b53d-108">Моделирование</span><span class="sxs-lookup"><span data-stu-id="7b53d-108">Modelling</span></span>

### <a name="basic-modelling"></a><span data-ttu-id="7b53d-109">Базовое моделирование</span><span class="sxs-lookup"><span data-stu-id="7b53d-109">Basic modelling</span></span>

<span data-ttu-id="7b53d-110">На основе сущностей POCO со свойствами get и set для стандартных скалярных типов (`int`, `string` и т. д.).</span><span class="sxs-lookup"><span data-stu-id="7b53d-110">Based on POCO entities with get/set properties of common scalar types (`int`, `string`, etc.).</span></span>

### <a name="relationships-and-navigation-properties"></a><span data-ttu-id="7b53d-111">Связи и свойства навигации</span><span class="sxs-lookup"><span data-stu-id="7b53d-111">Relationships and navigation properties</span></span>

<span data-ttu-id="7b53d-112">В модели на основе внешнего ключа можно создавать отношения "один ко многим" и "один к не более чем одному".</span><span class="sxs-lookup"><span data-stu-id="7b53d-112">One-to-many and One-to-zero-or-one relationships can be specified in the model based on a foreign key.</span></span> <span data-ttu-id="7b53d-113">С этими отношениями можно связать свойства навигации для простой коллекции или ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="7b53d-113">Navigation properties of simple collection or reference types can be associated with these relationships.</span></span>

### <a name="built-in-conventions"></a><span data-ttu-id="7b53d-114">Встроенные соглашения</span><span class="sxs-lookup"><span data-stu-id="7b53d-114">Built-in conventions</span></span>

<span data-ttu-id="7b53d-115">В этом варианте исходная модель создается на основе формы классов сущностей.</span><span class="sxs-lookup"><span data-stu-id="7b53d-115">These build an initial model based on the shape of the entity classes.</span></span>

### <a name="fluent-api"></a><span data-ttu-id="7b53d-116">Текучий API</span><span class="sxs-lookup"><span data-stu-id="7b53d-116">Fluent API</span></span>

<span data-ttu-id="7b53d-117">Позволяет переопределять метод `OnModelCreating` для пользовательского контекста, чтобы настраивать модель, обнаруженную на основе соглашений.</span><span class="sxs-lookup"><span data-stu-id="7b53d-117">Allows you to override the `OnModelCreating` method on your context to further configure the model that was discovered by convention.</span></span>

### <a name="data-annotations"></a><span data-ttu-id="7b53d-118">Заметки к данным</span><span class="sxs-lookup"><span data-stu-id="7b53d-118">Data annotations</span></span>

<span data-ttu-id="7b53d-119">Это атрибуты, которые можно добавлять в классы и (или) свойства сущности и которые будут влиять на модели EF.</span><span class="sxs-lookup"><span data-stu-id="7b53d-119">Are attributes that can be added to your entity classes/properties and will influence the EF model.</span></span> <span data-ttu-id="7b53d-120">Например, добавление `[Required]` сообщит платформе EF, что соответствующее свойство является обязательным.</span><span class="sxs-lookup"><span data-stu-id="7b53d-120">For example, adding `[Required]` will let EF know that a property is required.</span></span>

### <a name="relational-table-mapping"></a><span data-ttu-id="7b53d-121">Сопоставление в реляционной таблице</span><span class="sxs-lookup"><span data-stu-id="7b53d-121">Relational Table mapping</span></span>

<span data-ttu-id="7b53d-122">Позволяет сопоставить сущности с таблицами и (или) столбцами.</span><span class="sxs-lookup"><span data-stu-id="7b53d-122">Allows entities to be mapped to tables/columns.</span></span>

### <a name="key-value-generation"></a><span data-ttu-id="7b53d-123">Создание значений ключа</span><span class="sxs-lookup"><span data-stu-id="7b53d-123">Key value generation</span></span>

<span data-ttu-id="7b53d-124">Поддерживается создание на стороне клиентских процессов или в базе данных.</span><span class="sxs-lookup"><span data-stu-id="7b53d-124">Including client-side generation and database generation.</span></span>

### <a name="database-generated-values"></a><span data-ttu-id="7b53d-125">Созданные базой данных значения</span><span class="sxs-lookup"><span data-stu-id="7b53d-125">Database generated values</span></span>

<span data-ttu-id="7b53d-126">Позволяет базе данных создавать значения при вставке (для значений по умолчанию) или обновлении данных (для вычисляемых столбцов).</span><span class="sxs-lookup"><span data-stu-id="7b53d-126">Allows for values to be generated by the database on insert (default values) or update (computed columns).</span></span>

### <a name="sequences-in-sql-server"></a><span data-ttu-id="7b53d-127">Последовательности в SQL Server</span><span class="sxs-lookup"><span data-stu-id="7b53d-127">Sequences in SQL Server</span></span>

<span data-ttu-id="7b53d-128">Позволяет определить в модели объекты последовательностей.</span><span class="sxs-lookup"><span data-stu-id="7b53d-128">Allows for sequence objects to be defined in the model.</span></span>

### <a name="unique-constraints"></a><span data-ttu-id="7b53d-129">Ограничения уникальности</span><span class="sxs-lookup"><span data-stu-id="7b53d-129">Unique constraints</span></span>

<span data-ttu-id="7b53d-130">Позволяет определить альтернативные ключи и связи, использующие такие ключи.</span><span class="sxs-lookup"><span data-stu-id="7b53d-130">Allows for the definition of alternate keys and the ability to define relationships that target that key.</span></span>

### <a name="indexes"></a><span data-ttu-id="7b53d-131">Индексы</span><span class="sxs-lookup"><span data-stu-id="7b53d-131">Indexes</span></span>

<span data-ttu-id="7b53d-132">При определении индексов в модели они автоматически добавляются в базу данных.</span><span class="sxs-lookup"><span data-stu-id="7b53d-132">Defining indexes in the model automatically introduces indexes in the database.</span></span> <span data-ttu-id="7b53d-133">Поддерживаются также индексы UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="7b53d-133">Unique indexes are also supported.</span></span>

### <a name="shadow-state-properties"></a><span data-ttu-id="7b53d-134">Теневые свойства состояния</span><span class="sxs-lookup"><span data-stu-id="7b53d-134">Shadow state properties</span></span>

<span data-ttu-id="7b53d-135">Возможность определить в модели свойства, которые не объявляются и не хранятся в классе .NET, но отслеживаются и обновляются с помощью EF Core.</span><span class="sxs-lookup"><span data-stu-id="7b53d-135">Allows for properties to be defined in the model that are not declared and are not stored in the .NET class but can be tracked and updated by EF Core.</span></span> <span data-ttu-id="7b53d-136">Чаще всего применяется для свойств внешнего ключа, которые нежелательно отображать в самом объекте.</span><span class="sxs-lookup"><span data-stu-id="7b53d-136">Commonly used for foreign key properties when exposing these in the object is not desired.</span></span>

### <a name="table-per-hierarchy-inheritance-pattern"></a><span data-ttu-id="7b53d-137">Шаблон наследования "одна таблица на иерархию"</span><span class="sxs-lookup"><span data-stu-id="7b53d-137">Table-Per-Hierarchy inheritance pattern</span></span>

<span data-ttu-id="7b53d-138">Позволяет сохранять несколько сущностей иерархии в одну таблицу, в которой столбец дискриминатора определяет тип сущности для каждой записи в базе данных.</span><span class="sxs-lookup"><span data-stu-id="7b53d-138">Allows entities in an inheritance hierarchy to be saved to a single table using a discriminator column to identify they entity type for a given record in the database.</span></span>

### <a name="model-validation"></a><span data-ttu-id="7b53d-139">Проверка модели</span><span class="sxs-lookup"><span data-stu-id="7b53d-139">Model validation</span></span>

<span data-ttu-id="7b53d-140">Обнаруживает в модели неправильные соотношения и предоставляет полезные сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="7b53d-140">Detects invalid patterns in the model and provides helpful error messages.</span></span>

## <a name="change-tracking"></a><span data-ttu-id="7b53d-141">отслеживание изменений</span><span class="sxs-lookup"><span data-stu-id="7b53d-141">Change tracking</span></span>

### <a name="snapshot-change-tracking"></a><span data-ttu-id="7b53d-142">Отслеживание изменений по моментальному снимку</span><span class="sxs-lookup"><span data-stu-id="7b53d-142">Snapshot change tracking</span></span>

<span data-ttu-id="7b53d-143">Позволяет автоматически обнаруживать изменения в сущностях, сравнивая их текущее состояние с копией (моментальным снимком) исходного состояния.</span><span class="sxs-lookup"><span data-stu-id="7b53d-143">Allows changes in entities to be detected automatically by comparing current state against a copy (snapshot) of the original state.</span></span>

### <a name="notification-change-tracking"></a><span data-ttu-id="7b53d-144">Извещения об изменении состояния</span><span class="sxs-lookup"><span data-stu-id="7b53d-144">Notification change tracking</span></span>

<span data-ttu-id="7b53d-145">Позволяет создавать уведомления для отслеживающей стороны при изменении значений свойств.</span><span class="sxs-lookup"><span data-stu-id="7b53d-145">Allows your entities to notify the change tracker when property values are modified.</span></span>

### <a name="accessing-tracked-state"></a><span data-ttu-id="7b53d-146">Доступ к отслеживаемому состоянию</span><span class="sxs-lookup"><span data-stu-id="7b53d-146">Accessing tracked state</span></span>

<span data-ttu-id="7b53d-147">Осуществляется через `DbContext.Entry` и `DbContext.ChangeTracker`.</span><span class="sxs-lookup"><span data-stu-id="7b53d-147">Via `DbContext.Entry` and `DbContext.ChangeTracker`.</span></span>

### <a name="attaching-detached-entitiesgraphs"></a><span data-ttu-id="7b53d-148">Присоединение отсоединенных сущностей и диаграмм</span><span class="sxs-lookup"><span data-stu-id="7b53d-148">Attaching detached entities/graphs</span></span>

<span data-ttu-id="7b53d-149">Новый API `DbContext.AttachGraph` позволяет повторно присоединить сущности к контексту, чтобы избежать лишних операций создания или изменения объектов.</span><span class="sxs-lookup"><span data-stu-id="7b53d-149">The new `DbContext.AttachGraph` API helps re-attach entities to a context in order to save new/modified entities.</span></span>

## <a name="saving-data"></a><span data-ttu-id="7b53d-150">Сохранение данных</span><span class="sxs-lookup"><span data-stu-id="7b53d-150">Saving data</span></span>

### <a name="basic-save-functionality"></a><span data-ttu-id="7b53d-151">Основные возможности функции сохранения</span><span class="sxs-lookup"><span data-stu-id="7b53d-151">Basic save functionality</span></span>

<span data-ttu-id="7b53d-152">Изменения экземпляров сущности могут сохраняться в базу данных.</span><span class="sxs-lookup"><span data-stu-id="7b53d-152">Allows changes to entity instances to be persisted to the database.</span></span>

### <a name="optimistic-concurrency"></a><span data-ttu-id="7b53d-153">Оптимистический параллелизм</span><span class="sxs-lookup"><span data-stu-id="7b53d-153">Optimistic Concurrency</span></span>

<span data-ttu-id="7b53d-154">Защита от перезаписи изменений, внесенных другим пользователем после получения данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="7b53d-154">Protects against overwriting changes made by another user since data was fetched from the database.</span></span>

### <a name="async-savechanges"></a><span data-ttu-id="7b53d-155">Асинхронный метод сохранения SaveChanges</span><span class="sxs-lookup"><span data-stu-id="7b53d-155">Async SaveChanges</span></span>

<span data-ttu-id="7b53d-156">Позволяет освободить текущий поток для обработки других запросов, пока база данных обрабатывает команды от `SaveChanges`.</span><span class="sxs-lookup"><span data-stu-id="7b53d-156">Can free up the current thread to process other requests while the database processes the commands issued from `SaveChanges`.</span></span>

### <a name="database-transactions"></a><span data-ttu-id="7b53d-157">Транзакции базы данных</span><span class="sxs-lookup"><span data-stu-id="7b53d-157">Database Transactions</span></span>

<span data-ttu-id="7b53d-158">Означает, что `SaveChanges` всегда является атомарной (то есть либо завершается успешно полностью, либо не вносит никаких изменений в базу данных).</span><span class="sxs-lookup"><span data-stu-id="7b53d-158">Means that `SaveChanges` is always atomic (meaning it either completely succeeds, or no changes are made to the database).</span></span> <span data-ttu-id="7b53d-159">Также для транзакций предоставлены специальные API, которые позволяют совместно использовать транзакции в нескольких экземплярах контекста и т. д.</span><span class="sxs-lookup"><span data-stu-id="7b53d-159">There are also transaction related APIs to allow sharing transactions between context instances etc.</span></span>

### <a name="relational-batching-of-statements"></a><span data-ttu-id="7b53d-160">Реляционные базы данных: пакетная обработка инструкций</span><span class="sxs-lookup"><span data-stu-id="7b53d-160">Relational: Batching of statements</span></span>

<span data-ttu-id="7b53d-161">Повышает производительность, выполняя несколько команд INSERT/UPDATE/DELETE за одно обращение к базе данных.</span><span class="sxs-lookup"><span data-stu-id="7b53d-161">Provides better performance by batching up multiple INSERT/UPDATE/DELETE commands into a single roundtrip to the database.</span></span>

## <a name="query"></a><span data-ttu-id="7b53d-162">Запрос</span><span class="sxs-lookup"><span data-stu-id="7b53d-162">Query</span></span>

### <a name="basic-linq-support"></a><span data-ttu-id="7b53d-163">Базовая поддержка LINQ</span><span class="sxs-lookup"><span data-stu-id="7b53d-163">Basic LINQ support</span></span>

<span data-ttu-id="7b53d-164">Предоставляет возможность использовать LINQ для извлечения данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="7b53d-164">Provides the ability to use LINQ to retrieve data from the database.</span></span>

### <a name="mixed-clientserver-evaluation"></a><span data-ttu-id="7b53d-165">Смешанное вычисление на клиенте и сервере</span><span class="sxs-lookup"><span data-stu-id="7b53d-165">Mixed client/server evaluation</span></span>

<span data-ttu-id="7b53d-166">Позволяет включать в запросы логику, которая не может быть выполнена в базе данных, и обрабатывать ее уже после получения данных в память.</span><span class="sxs-lookup"><span data-stu-id="7b53d-166">Enables queries to contain logic that cannot be evaluated in the database, and must therefore be evaluated after the data is retrieved into memory.</span></span>

### <a name="notracking"></a><span data-ttu-id="7b53d-167">NoTracking</span><span class="sxs-lookup"><span data-stu-id="7b53d-167">NoTracking</span></span>

<span data-ttu-id="7b53d-168">Запросы выполняются быстрее, если контекст не отслеживает изменения экземпляров сущностей (это полезно, если результаты доступны только для чтения).</span><span class="sxs-lookup"><span data-stu-id="7b53d-168">Queries enables quicker query execution when the context does not need to monitor for changes to the entity instances (this is useful if the results are read-only).</span></span>

### <a name="eager-loading"></a><span data-ttu-id="7b53d-169">Безотложная загрузка</span><span class="sxs-lookup"><span data-stu-id="7b53d-169">Eager loading</span></span>

<span data-ttu-id="7b53d-170">Предоставляет методы `Include` и `ThenInclude` для определения смежных данных, которые нужно извлекать вместе с основным запросом.</span><span class="sxs-lookup"><span data-stu-id="7b53d-170">Provides the `Include` and `ThenInclude` methods to identify related data that should also be fetched when querying.</span></span>

### <a name="async-query"></a><span data-ttu-id="7b53d-171">Асинхронный запрос</span><span class="sxs-lookup"><span data-stu-id="7b53d-171">Async query</span></span>

<span data-ttu-id="7b53d-172">Позволяет освободить текущий поток и его ресурсы для обработки других запросов, пока база данных обрабатывает текущий запрос.</span><span class="sxs-lookup"><span data-stu-id="7b53d-172">Can free up the current thread (and it's associated resources) to process other requests while the database processes the query.</span></span>

### <a name="raw-sql-queries"></a><span data-ttu-id="7b53d-173">Необработанные SQL-запросы</span><span class="sxs-lookup"><span data-stu-id="7b53d-173">Raw SQL queries</span></span>

<span data-ttu-id="7b53d-174">Предоставляет метод `DbSet.FromSql` для получения данных с помощью необработанных SQL-запросов.</span><span class="sxs-lookup"><span data-stu-id="7b53d-174">Provides the `DbSet.FromSql` method to use raw SQL queries to fetch data.</span></span> <span data-ttu-id="7b53d-175">Эти запросы можно также создавать с помощью LINQ.</span><span class="sxs-lookup"><span data-stu-id="7b53d-175">These queries can also be composed on using LINQ.</span></span>

## <a name="database-schema-management"></a><span data-ttu-id="7b53d-176">Управление схемой базы данных</span><span class="sxs-lookup"><span data-stu-id="7b53d-176">Database schema management</span></span>

### <a name="database-creationdeletion-apis"></a><span data-ttu-id="7b53d-177">Интерфейсы API для создания и удаления баз данных</span><span class="sxs-lookup"><span data-stu-id="7b53d-177">Database creation/deletion APIs</span></span>

<span data-ttu-id="7b53d-178">Предназначены в основном для тестирования, при котором часто бывает нужно быстро создать или удалить базу данных без использования миграции.</span><span class="sxs-lookup"><span data-stu-id="7b53d-178">Are mostly designed for testing where you want to quickly create/delete the database without using migrations.</span></span>

### <a name="relational-database-migrations"></a><span data-ttu-id="7b53d-179">Миграции реляционной базы данных</span><span class="sxs-lookup"><span data-stu-id="7b53d-179">Relational database migrations</span></span>

<span data-ttu-id="7b53d-180">Позволяет изменять схему реляционной базы данных параллельно с развитием модели.</span><span class="sxs-lookup"><span data-stu-id="7b53d-180">Allow a relational database schema to evolve overtime as your model changes.</span></span>

### <a name="reverse-engineer-from-database"></a><span data-ttu-id="7b53d-181">Реконструирование из базы данных</span><span class="sxs-lookup"><span data-stu-id="7b53d-181">Reverse engineer from database</span></span>

<span data-ttu-id="7b53d-182">Создает модель EF на основе существующей схемы реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="7b53d-182">Scaffolds an EF model based on an existing relational database schema.</span></span>

## <a name="database-providers"></a><span data-ttu-id="7b53d-183">Поставщики баз данных</span><span class="sxs-lookup"><span data-stu-id="7b53d-183">Database providers</span></span>

### <a name="sql-server"></a><span data-ttu-id="7b53d-184">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7b53d-184">SQL Server</span></span>

<span data-ttu-id="7b53d-185">Позволяет подключаться к Microsoft SQL Server 2008 и более новых версий.</span><span class="sxs-lookup"><span data-stu-id="7b53d-185">Connects to Microsoft SQL Server 2008 onwards.</span></span>

### <a name="sqlite"></a><span data-ttu-id="7b53d-186">SQLite</span><span class="sxs-lookup"><span data-stu-id="7b53d-186">SQLite</span></span>

<span data-ttu-id="7b53d-187">Позволяет подключаться к базе данных SQLite 3.</span><span class="sxs-lookup"><span data-stu-id="7b53d-187">Connects to a SQLite 3 database.</span></span>

### <a name="in-memory"></a><span data-ttu-id="7b53d-188">В памяти</span><span class="sxs-lookup"><span data-stu-id="7b53d-188">In-Memory</span></span>

<span data-ttu-id="7b53d-189">Позволяет легко выполнять тестирование без подключения к настоящим базам данных.</span><span class="sxs-lookup"><span data-stu-id="7b53d-189">Is designed to easily enable testing without connecting to a real database.</span></span>

### <a name="3rd-party-providers"></a><span data-ttu-id="7b53d-190">Сторонние поставщики</span><span class="sxs-lookup"><span data-stu-id="7b53d-190">3rd party providers</span></span>

<span data-ttu-id="7b53d-191">Поддерживаются несколько поставщиков других ядер СУБД.</span><span class="sxs-lookup"><span data-stu-id="7b53d-191">Several providers are available for other database engines.</span></span> <span data-ttu-id="7b53d-192">Полный их список можно найти в статье [Database Providers](../providers/index.md) (Поставщики баз данных).</span><span class="sxs-lookup"><span data-stu-id="7b53d-192">See [Database Providers](../providers/index.md) for a complete list.</span></span>
