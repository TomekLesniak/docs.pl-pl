---
description: Odwołanie do języka C#
title: Odwołanie do języka C#
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: 4712a6906195c5d8bc09c7b734dba0df4d2b08c8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134526"
---
# <a name="into-c-reference"></a>into (odwołanie w C#)

`into`Kontekstowe słowo kluczowe może służyć do tworzenia tymczasowego identyfikatora do przechowywania wyników [grupy](group-clause.md), [sprzężenia](join-clause.md) lub [zaznaczania](select-clause.md) do nowego identyfikatora. Ten identyfikator może być generatorem dla dodatkowych poleceń zapytań. W przypadku użycia w `group` `select` klauzuli OR, użycie nowego identyfikatora jest czasami określane jako *kontynuacja*.

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano użycie `into` słowa kluczowego, aby włączyć tymczasowy identyfikator `fruitGroup` , który ma wnioskowany typ `IGrouping` . Używając identyfikatora, można wywołać <xref:System.Linq.Enumerable.Count%2A> metodę dla każdej grupy i wybrać tylko te grupy, które zawierają dwa lub więcej wyrazów.

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

Użycie `into` w `group` klauzuli jest wymagane tylko wtedy, gdy chcesz wykonać dodatkowe operacje na zapytania dla każdej grupy. Aby uzyskać więcej informacji, zobacz [klauzula](group-clause.md)Group.

Aby zapoznać się z przykładem użycia `into` w `join` klauzuli, zobacz [Klauzula join](join-clause.md).

## <a name="see-also"></a>Zobacz też

- [Słowa kluczowe zapytania (LINQ)](query-keywords.md)
- [LINQ w C#](../../linq/index.md)
- [group — Klauzula](group-clause.md)
