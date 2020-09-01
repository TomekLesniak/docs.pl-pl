---
description: OrderBy — klauzula — odwołanie w C#
title: OrderBy — klauzula — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: 2f64b45ff252c7cc02e56c465da21ccc5e861aec
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142352"
---
# <a name="orderby-clause-c-reference"></a>Klauzula orderby (odwołanie w C#)

W wyrażeniu zapytania, `orderby` klauzula powoduje, że zwracana sekwencja lub podsekwencja (Grupa) ma być sortowana w kolejności rosnącej lub malejącej. Można określić wiele kluczy, aby wykonać jedną lub więcej pomocniczych operacji sortowania. Sortowanie jest wykonywane przez domyślną funkcję porównującą dla typu elementu. Domyślna kolejność sortowania to Ascending. Można również określić niestandardową funkcję porównującą. Jednak jest on dostępny tylko przy użyciu składni opartej na metodzie. Aby uzyskać więcej informacji, zobacz [Sortowanie danych](../../programming-guide/concepts/linq/sorting-data.md).

## <a name="example"></a>Przykład

W poniższym przykładzie pierwsze zapytanie sortuje wyrazy w kolejności alfabetycznej, zaczynając od A, a drugie zapytanie sortuje te same wyrazy w kolejności malejącej. ( `ascending` Słowo kluczowe jest domyślną wartością sortowania i można je pominąć).

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a>Przykład

Poniższy przykład wykonuje sortowanie podstawowe dla nazwisk uczniów, a następnie pomocnicze sortowanie według ich imion.

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a>Uwagi

W czasie kompilacji `orderby` klauzula jest tłumaczona na wywołanie <xref:System.Linq.Enumerable.OrderBy%2A> metody. Wiele kluczy w `orderby` klauzuli jest przetłumaczyć na <xref:System.Linq.Enumerable.ThenBy%2A> wywołania metod.

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Słowa kluczowe zapytania (LINQ)](query-keywords.md)
- [LINQ w C#](../../linq/index.md)
- [group — Klauzula](group-clause.md)
- [Language Integrated Query (LINQ)](../../programming-guide/concepts/linq/index.md)
