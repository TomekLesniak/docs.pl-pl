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
# <a name="async-limitations"></a>Ograniczenia asynchroniczne

SQLite nie obsługuje asynchronicznych operacji we/wy. Asynchroniczne metody ADO.NET będą wykonywane synchronicznie w programie Microsoft. Data. sqlite. Należy unikać wywoływania tych funkcji.

Zamiast tego należy użyć [udostępnionej pamięci podręcznej](connection-strings.md#cache) i [rejestrowania z wyprzedzeniem](https://www.sqlite.org/wal.html) w celu zwiększenia wydajności i współbieżności.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> Rejestrowanie z wyprzedzeniem jest domyślnie włączone w bazach danych utworzonych przy użyciu [Entity Framework Core](/ef/core/).
