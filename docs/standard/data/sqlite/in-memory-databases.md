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
# <a name="in-memory-databases"></a>Bazy danych w pamięci

Bazy danych w pamięci programu SQLite są bazami danych przechowywanymi w całości w pamięci, a nie na dysku. Użyj nazwy pliku specjalnej źródła danych, `:memory:` Aby utworzyć bazę danych w pamięci. Po zamknięciu połączenia baza danych zostanie usunięta. W przypadku korzystania `:memory:` z programu każde połączenie tworzy własną bazę danych.

```connectionstring
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>Współużytkowane bazy danych w pamięci

Bazy danych w pamięci mogą być współużytkowane przez wiele połączeń przy użyciu `Mode=Memory` i `Cache=Shared` w parametrach połączenia. `Data Source`Słowo kluczowe jest używane do nadania nazwy bazy danych znajdującej się w pamięci. Parametry połączenia używające tej samej nazwy będą miały dostęp do tej samej bazy danych w pamięci. Baza danych utrzymuje się, dopóki nie zostanie otwarte co najmniej jedno połączenie. [Przykład](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) pokazujący, że jest dostępny w serwisie GitHub.

```connectionstring
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
