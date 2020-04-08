---
title: Асинхронное сохранение — EF Core
author: rowanmiller
ms.date: 01/24/2017
ms.assetid: b64a606e-ecd9-4807-829a-b6ec05ade33f
uid: core/saving/async
ms.openlocfilehash: 0823b86f0579dd3e42f6bd2aebfb433d3cbe00ab
ms.sourcegitcommit: 9b562663679854c37c05fca13d93e180213fb4aa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "78413693"
---
# <a name="asynchronous-saving"></a>Асинхронное сохранение

Асинхронное сохранение позволяет избежать блокировки потока при записи изменений в базу данных. Эта функция помогает предотвратить замораживание пользовательского интерфейса многофункционального клиентского приложения. Асинхронные операции могут также увеличить пропускную способность в веб-приложении, где можно высвободить поток для обработки других запросов во время завершения операции базы данных. Дополнительные сведения см. в статье об [асинхронном программировании на C#](https://docs.microsoft.com/dotnet/csharp/async).

> [!WARNING]  
> EF Core не поддерживает выполнение нескольких параллельных операций в одном экземпляре контекста. Следует подождать завершения одной операции, прежде чем запускать следующую. Для этого обычно нужно указать ключевое слово `await` в каждой асинхронной операции.

Entity Framework Core предоставляет `DbContext.SaveChangesAsync()` в качестве асинхронной альтернативы `DbContext.SaveChanges()`.

[!code-csharp[Main](../../../samples/core/Saving/Async/Sample.cs#Sample)]
