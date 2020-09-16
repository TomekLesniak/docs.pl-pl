---
title: Bazy danych w pamięci
ms.date: 12/13/2019
description: Dowiedz się, jak używać baz danych programu SQLite w pamięci.
ms.openlocfilehash: fbda5787d95a9ce462752b985f847af0b0551fa6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555370"
---
# <a name="in-memory-databases"></a><span data-ttu-id="16f07-103">Bazy danych w pamięci</span><span class="sxs-lookup"><span data-stu-id="16f07-103">In-memory databases</span></span>

<span data-ttu-id="16f07-104">Bazy danych w pamięci programu SQLite są bazami danych przechowywanymi w całości w pamięci, a nie na dysku.</span><span class="sxs-lookup"><span data-stu-id="16f07-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="16f07-105">Użyj nazwy pliku specjalnej źródła danych, `:memory:` Aby utworzyć bazę danych w pamięci.</span><span class="sxs-lookup"><span data-stu-id="16f07-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="16f07-106">Po zamknięciu połączenia baza danych zostanie usunięta.</span><span class="sxs-lookup"><span data-stu-id="16f07-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="16f07-107">W przypadku korzystania `:memory:` z programu każde połączenie tworzy własną bazę danych.</span><span class="sxs-lookup"><span data-stu-id="16f07-107">When using `:memory:`, each connection creates its own database.</span></span>

```connectionstring
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="16f07-108">Współużytkowane bazy danych w pamięci</span><span class="sxs-lookup"><span data-stu-id="16f07-108">Shareable in-memory databases</span></span>

<span data-ttu-id="16f07-109">Bazy danych w pamięci mogą być współużytkowane przez wiele połączeń przy użyciu `Mode=Memory` i `Cache=Shared` w parametrach połączenia.</span><span class="sxs-lookup"><span data-stu-id="16f07-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="16f07-110">`Data Source`Słowo kluczowe jest używane do nadania nazwy bazy danych znajdującej się w pamięci.</span><span class="sxs-lookup"><span data-stu-id="16f07-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="16f07-111">Parametry połączenia używające tej samej nazwy będą miały dostęp do tej samej bazy danych w pamięci.</span><span class="sxs-lookup"><span data-stu-id="16f07-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="16f07-112">Baza danych utrzymuje się, dopóki nie zostanie otwarte co najmniej jedno połączenie.</span><span class="sxs-lookup"><span data-stu-id="16f07-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="16f07-113">[Przykład](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) pokazujący, że jest dostępny w serwisie GitHub.</span><span class="sxs-lookup"><span data-stu-id="16f07-113">A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```connectionstring
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
