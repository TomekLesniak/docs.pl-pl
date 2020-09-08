---
title: Ograniczenia asynchroniczne
ms.date: 09/04/2020
description: Wyjaśnia ograniczenia dotyczące asynchronicznych interfejsów API i niektórych alternatyw, których można użyć zamiast tego.
ms.openlocfilehash: 8b14fcfeb12d331d8d43ca6d77332007a12ae5dc
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89515998"
---
# <a name="async-limitations"></a><span data-ttu-id="9ff73-103">Ograniczenia asynchroniczne</span><span class="sxs-lookup"><span data-stu-id="9ff73-103">Async limitations</span></span>

<span data-ttu-id="9ff73-104">SQLite nie obsługuje asynchronicznych operacji we/wy.</span><span class="sxs-lookup"><span data-stu-id="9ff73-104">SQLite doesn't support asynchronous I/O.</span></span> <span data-ttu-id="9ff73-105">Asynchroniczne metody ADO.NET będą wykonywane synchronicznie w programie Microsoft. Data. sqlite.</span><span class="sxs-lookup"><span data-stu-id="9ff73-105">Async ADO.NET methods will execute synchronously in Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="9ff73-106">Należy unikać wywoływania tych funkcji.</span><span class="sxs-lookup"><span data-stu-id="9ff73-106">Avoid calling them.</span></span>

<span data-ttu-id="9ff73-107">Zamiast tego należy użyć [udostępnionej pamięci podręcznej](connection-strings.md#cache) i [rejestrowania z wyprzedzeniem](https://www.sqlite.org/wal.html) w celu zwiększenia wydajności i współbieżności.</span><span class="sxs-lookup"><span data-stu-id="9ff73-107">Instead, use a [shared cache](connection-strings.md#cache) and [write-ahead logging](https://www.sqlite.org/wal.html) to improve performance and concurrency.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> <span data-ttu-id="9ff73-108">Rejestrowanie z wyprzedzeniem jest domyślnie włączone w bazach danych utworzonych przy użyciu [Entity Framework Core](/ef/core/).</span><span class="sxs-lookup"><span data-stu-id="9ff73-108">Write-ahead logging is enabled by default on databases created using [Entity Framework Core](/ef/core/).</span></span>
