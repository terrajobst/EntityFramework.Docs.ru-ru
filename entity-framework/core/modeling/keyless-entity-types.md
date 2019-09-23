---
title: Типы сущностей без ключей — EF Core
author: AndriySvyryd
ms.author: ansvyryd
ms.date: 02/26/2018
ms.assetid: 9F4450C5-1A3F-4BB6-AC19-9FAC64292AAD
uid: core/modeling/keyless-entity-types
ms.openlocfilehash: b968ac9602b9aa1f1c1e3181b6b76a64394d70f0
ms.sourcegitcommit: cbaa6cc89bd71d5e0bcc891e55743f0e8ea3393b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "71150791"
---
# <a name="keyless-entity-types"></a><span data-ttu-id="5df1d-102">Типы сущностей без ключей</span><span class="sxs-lookup"><span data-stu-id="5df1d-102">Keyless Entity Types</span></span>
> [!NOTE]
> <span data-ttu-id="5df1d-103">Это новая возможность в EF Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="5df1d-103">This feature is new in EF Core 2.1.</span></span> <span data-ttu-id="5df1d-104">До 3,0 они назывались типами запросов</span><span class="sxs-lookup"><span data-stu-id="5df1d-104">Prior to 3.0 they were known as Query Types</span></span>

<span data-ttu-id="5df1d-105">В дополнение к обычным типам сущностей модель EF Core может содержать незашифрованные _типы сущностей_, которые можно использовать для выполнения запросов к базе данных, не содержащей значений ключей.</span><span class="sxs-lookup"><span data-stu-id="5df1d-105">In addition to regular entity types, an EF Core model can contain _keyless entity types_, which can be used to carry out database queries against data that doesn't contain key values.</span></span>

## <a name="keyless-entity-types-characteristics"></a><span data-ttu-id="5df1d-106">Характеристики типов сущностей без ключей</span><span class="sxs-lookup"><span data-stu-id="5df1d-106">Keyless entity types characteristics</span></span>

<span data-ttu-id="5df1d-107">Типы сущностей без ключей поддерживают многие из тех же возможностей сопоставления, что и обычные типы сущностей, такие как сопоставление наследования и свойства навигации.</span><span class="sxs-lookup"><span data-stu-id="5df1d-107">Keyless entity types support many of the same mapping capabilities as regular entity types, like inheritance mapping and navigation properties.</span></span> <span data-ttu-id="5df1d-108">В реляционных хранилищах их можно настроить объекты целевой базы данных и столбцы с помощью текучего API методы или заметки к данным.</span><span class="sxs-lookup"><span data-stu-id="5df1d-108">On relational stores, they can configure the target database objects and columns via fluent API methods or data annotations.</span></span>

<span data-ttu-id="5df1d-109">Однако они отличаются от обычных типов сущностей тем, что они:</span><span class="sxs-lookup"><span data-stu-id="5df1d-109">However, they are different from regular entity types in that they:</span></span>

- <span data-ttu-id="5df1d-110">Ключ не может быть определен.</span><span class="sxs-lookup"><span data-stu-id="5df1d-110">Cannot have a key defined.</span></span>
- <span data-ttu-id="5df1d-111">Никогда не отправляются для изменений в _DbContext_ , поэтому они никогда не вставляются, не обновляются или не удаляются в базе данных.</span><span class="sxs-lookup"><span data-stu-id="5df1d-111">Are never tracked for changes in the _DbContext_ and therefore are never inserted, updated or deleted on the database.</span></span>
- <span data-ttu-id="5df1d-112">Никогда не обнаруживаются по соглашению.</span><span class="sxs-lookup"><span data-stu-id="5df1d-112">Are never discovered by convention.</span></span>
- <span data-ttu-id="5df1d-113">Поддерживаются только подмножество возможностей сопоставления навигации, в частности:</span><span class="sxs-lookup"><span data-stu-id="5df1d-113">Only support a subset of navigation mapping capabilities, specifically:</span></span>
  - <span data-ttu-id="5df1d-114">Они никогда не может выступать в качестве основной конец связи.</span><span class="sxs-lookup"><span data-stu-id="5df1d-114">They may never act as the principal end of a relationship.</span></span>
  - <span data-ttu-id="5df1d-115">Они не могут иметь переходы к собственным сущностям</span><span class="sxs-lookup"><span data-stu-id="5df1d-115">They may not have navigations to owned entities</span></span>
  - <span data-ttu-id="5df1d-116">Они могут содержать только свойства навигации по ссылке, указывающие на обычные сущности.</span><span class="sxs-lookup"><span data-stu-id="5df1d-116">They can only contain reference navigation properties pointing to regular entities.</span></span>
  - <span data-ttu-id="5df1d-117">Сущности не могут содержать свойства навигации для неключейых типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="5df1d-117">Entities cannot contain navigation properties to keyless entity types.</span></span>
- <span data-ttu-id="5df1d-118">Необходимо настроить с помощью `.HasNoKey()` вызова метода.</span><span class="sxs-lookup"><span data-stu-id="5df1d-118">Need to be configured with `.HasNoKey()` method call.</span></span>
- <span data-ttu-id="5df1d-119">Может быть сопоставлен с _определяющим запросом_.</span><span class="sxs-lookup"><span data-stu-id="5df1d-119">May be mapped to a _defining query_.</span></span> <span data-ttu-id="5df1d-120">Определяющий запрос — это запрос, объявленный в модели, который выступает в качестве источника данных для типа сущности без ключей.</span><span class="sxs-lookup"><span data-stu-id="5df1d-120">A defining query is a query declared in the model that acts as a data source for a keyless entity type.</span></span>

## <a name="usage-scenarios"></a><span data-ttu-id="5df1d-121">Сценарии использования</span><span class="sxs-lookup"><span data-stu-id="5df1d-121">Usage scenarios</span></span>

<span data-ttu-id="5df1d-122">Ниже приведены некоторые основные сценарии использования для типов сущностей без ключей:</span><span class="sxs-lookup"><span data-stu-id="5df1d-122">Some of the main usage scenarios for keyless entity types are:</span></span>

- <span data-ttu-id="5df1d-123">Служит типом возвращаемого значения для [необработанных запросов SQL](xref:core/querying/raw-sql).</span><span class="sxs-lookup"><span data-stu-id="5df1d-123">Serving as the return type for [raw SQL queries](xref:core/querying/raw-sql).</span></span>
- <span data-ttu-id="5df1d-124">Сопоставление с представлениями базы данных, которые не содержат первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="5df1d-124">Mapping to database views that do not contain a primary key.</span></span>
- <span data-ttu-id="5df1d-125">Сопоставление таблиц, у которых не определен первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="5df1d-125">Mapping to tables that do not have a primary key defined.</span></span>
- <span data-ttu-id="5df1d-126">Сопоставление с запросами, определенными в модели.</span><span class="sxs-lookup"><span data-stu-id="5df1d-126">Mapping to queries defined in the model.</span></span>

## <a name="mapping-to-database-objects"></a><span data-ttu-id="5df1d-127">Сопоставление объектов базы данных</span><span class="sxs-lookup"><span data-stu-id="5df1d-127">Mapping to database objects</span></span>

<span data-ttu-id="5df1d-128">Сопоставление типа сущности без ключей с объектом базы данных достигается с помощью `ToTable` API `ToView` -интерфейса или Fluent.</span><span class="sxs-lookup"><span data-stu-id="5df1d-128">Mapping a keyless entity type to a database object is achieved using the `ToTable` or `ToView` fluent API.</span></span> <span data-ttu-id="5df1d-129">С точки зрения EF Core, является объект базы данных, указанный в этом методе _представление_, это означает, что она обрабатывается как источник запроса только для чтения и не может быть целевым объектом update, insert или delete операций.</span><span class="sxs-lookup"><span data-stu-id="5df1d-129">From the perspective of EF Core, the database object specified in this method is a _view_, meaning that it is treated as a read-only query source and cannot be the target of update, insert or delete operations.</span></span> <span data-ttu-id="5df1d-130">Однако это не означает, что объект базы данных действительно должен быть представлением базы данных.</span><span class="sxs-lookup"><span data-stu-id="5df1d-130">However, this does not mean that the database object is actually required to be a database view.</span></span> <span data-ttu-id="5df1d-131">В качестве альтернативы можно использовать таблицу базы данных, которая будет рассматриваться как доступная только для чтения.</span><span class="sxs-lookup"><span data-stu-id="5df1d-131">It can alternatively be a database table that will be treated as read-only.</span></span> <span data-ttu-id="5df1d-132">И наоборот, для обычных типов сущностей EF Core предполагается, что объект базы данных, указанный `ToTable` в методе, может рассматриваться как _Таблица_, что означает, что он может использоваться в качестве источника запроса, но также предназначен для операций обновления, удаления и вставки.</span><span class="sxs-lookup"><span data-stu-id="5df1d-132">Conversely, for regular entity types, EF Core assumes that a database object specified in the `ToTable` method can be treated as a _table_, meaning that it can be used as a query source but also targeted by update, delete and insert operations.</span></span> <span data-ttu-id="5df1d-133">На самом деле, можно указать имя представления базы данных в `ToTable` и все должно работать нормально, пока представление настроено как обновляемые в базе данных.</span><span class="sxs-lookup"><span data-stu-id="5df1d-133">In fact, you can specify the name of a database view in `ToTable` and everything should work fine as long as the view is configured to be updatable on the database.</span></span>

> [!NOTE]
> <span data-ttu-id="5df1d-134">`ToView`Предполагается, что объект уже существует в базе данных и не создается при миграции.</span><span class="sxs-lookup"><span data-stu-id="5df1d-134">`ToView` assumes that the object already exists in the database and it won't be created by migrations.</span></span>

## <a name="example"></a><span data-ttu-id="5df1d-135">Пример</span><span class="sxs-lookup"><span data-stu-id="5df1d-135">Example</span></span>

<span data-ttu-id="5df1d-136">В следующем примере показано, как использовать типы сущностей без ключей для запроса представления базы данных.</span><span class="sxs-lookup"><span data-stu-id="5df1d-136">The following example shows how to use keyless entity types to query a database view.</span></span>

> [!TIP]
> <span data-ttu-id="5df1d-137">Для этой статьи вы можете скачать [пример](https://github.com/aspnet/EntityFramework.Docs/tree/master/samples/core/QueryTypes) из репозитория GitHub.</span><span class="sxs-lookup"><span data-stu-id="5df1d-137">You can view this article's [sample](https://github.com/aspnet/EntityFramework.Docs/tree/master/samples/core/QueryTypes) on GitHub.</span></span>

<span data-ttu-id="5df1d-138">Во-первых определим простую модель блога и Post.</span><span class="sxs-lookup"><span data-stu-id="5df1d-138">First, we define a simple Blog and Post model:</span></span>

[!code-csharp[Main](../../../samples/core/KeylessEntityTypes/Program.cs#Entities)]

<span data-ttu-id="5df1d-139">Далее мы определим представление простой базы данных, которые позволят нам запросить число сообщений, связанных с каждого блога:</span><span class="sxs-lookup"><span data-stu-id="5df1d-139">Next, we define a simple database view that will allow us to query the number of posts associated with each blog:</span></span>

[!code-csharp[Main](../../../samples/core/KeylessEntityTypes/Program.cs#View)]

<span data-ttu-id="5df1d-140">Далее мы определим класс для хранения результата из представления базы данных:</span><span class="sxs-lookup"><span data-stu-id="5df1d-140">Next, we define a class to hold the result from the database view:</span></span>

[!code-csharp[Main](../../../samples/core/KeylessEntityTypes/Program.cs#KeylessEntityType)]

<span data-ttu-id="5df1d-141">Далее мы настроим тип сущности без ключей в _OnModelCreating_ с помощью `HasNoKey` API.</span><span class="sxs-lookup"><span data-stu-id="5df1d-141">Next, we configure the keyless entity type in _OnModelCreating_ using the `HasNoKey` API.</span></span>
<span data-ttu-id="5df1d-142">Мы используем API-интерфейс конфигурации Fluent для настройки сопоставления для типа сущности без ключей:</span><span class="sxs-lookup"><span data-stu-id="5df1d-142">We use fluent configuration API to configure the mapping for the keyless entity type:</span></span>

[!code-csharp[Main](../../../samples/core/KeylessEntityTypes/Program.cs#Configuration)]

<span data-ttu-id="5df1d-143">Далее мы настроим `DbContext` для `DbSet<T>`включения:</span><span class="sxs-lookup"><span data-stu-id="5df1d-143">Next, we configure the `DbContext` to include the `DbSet<T>`:</span></span>

[!code-csharp[Main](../../../samples/core/KeylessEntityTypes/Program.cs#DbSet)]

<span data-ttu-id="5df1d-144">Наконец можно запросить представления базы данных обычным образом:</span><span class="sxs-lookup"><span data-stu-id="5df1d-144">Finally, we can query the database view in the standard way:</span></span>

[!code-csharp[Main](../../../samples/core/KeylessEntityTypes/Program.cs#Query)]

> [!TIP]
> <span data-ttu-id="5df1d-145">Обратите внимание, что мы также определили свойство запроса уровня контекста (DbSet), которое будет использоваться в качестве корневого для запросов к этому типу.</span><span class="sxs-lookup"><span data-stu-id="5df1d-145">Note we have also defined a context level query property (DbSet) to act as a root for queries against this type.</span></span>