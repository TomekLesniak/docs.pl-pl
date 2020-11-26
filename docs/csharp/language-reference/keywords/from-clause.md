---
description: Klauzula from — odwołanie w C#
title: Klauzula from — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- from_CSharpKeyword
- from
helpviewer_keywords:
- from clause [C#]
- from keyword [C#]
ms.assetid: 1aefd18c-1314-47f8-99ec-9bcefb09e699
ms.openlocfilehash: 474b22f5a9d8f12c8a4365159817f878761b563c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "89140792"
---
# <a name="from-clause-c-reference"></a>Klauzula From (odwołanie w C#)

Wyrażenie zapytania musi rozpoczynać się od `from` klauzuli. Ponadto wyrażenie zapytania może zawierać podzapytania, które również zaczynają się od `from` klauzuli. `from`Klauzula określa następujące elementy:

- Źródło danych, w którym zostanie uruchomione zapytanie lub podzapytanie.

- Lokalna *zmienna zakresu* , która reprezentuje każdy element w sekwencji źródłowej.

Zarówno zmienna zakresu, jak i źródło danych, są jednoznacznie wpisane. Źródło danych, do którego istnieje odwołanie w `from` klauzuli, musi mieć typ <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> lub typ pochodny, taki jak <xref:System.Linq.IQueryable%601> .

W poniższym przykładzie `numbers` jest źródłem danych i `num` jest zmienną zakresu. Należy zauważyć, że obie zmienne są silnie określone, mimo że jest używane słowo kluczowe [var](var.md) .

[!code-csharp[cscsrefQueryKeywords#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/From.cs#1)]

## <a name="the-range-variable"></a>Zmienna zakresu

Kompilator wnioskuje typ zmiennej zakresu podczas implementowania źródła danych <xref:System.Collections.Generic.IEnumerable%601> . Na przykład, jeśli źródło ma typ `IEnumerable<Customer>` , zmienna zakresu jest wywnioskowana `Customer` . Jedynym warunkiem, że należy określić typ jawnie, jest to, że źródło jest typem nieogólnym `IEnumerable` , takim jak <xref:System.Collections.ArrayList> . Aby uzyskać więcej informacji, zobacz [How to Query The ArrayList with LINQ](../../programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md).

W poprzednim przykładzie `num` jest wnioskowany jako typ `int` . Ponieważ zmienna zakresu jest silnie wpisana, można wywołać metody lub użyć jej w innych operacjach. Na przykład zamiast pisać `select num` można napisać, `select num.ToString()` Aby spowodować, że wyrażenie zapytania zwróci sekwencję ciągów zamiast liczb całkowitych. Lub można napisać, `select num + 10` aby wyrażenie zwracało sekwencję 14, 11, 13, 12, 10. Aby uzyskać więcej informacji, zobacz [SELECT — klauzula](select-clause.md).

Zmienna zakresu jest jak Zmienna iteracji w instrukcji [foreach](foreach-in.md) z wyjątkiem jednej bardzo ważnej różnicy: zmienna zakresu nigdy nie przechowuje danych ze źródła. Jest to tylko wygoda syntaktyczna, która umożliwia zapytanie opisującym, co się dzieje po wykonaniu zapytania. Aby uzyskać więcej informacji, zobacz [wprowadzenie do zapytań LINQ (C#)](../../programming-guide/concepts/linq/introduction-to-linq-queries.md).

## <a name="compound-from-clauses"></a>Złożone z klauzul

W niektórych przypadkach każdy element w sekwencji źródłowej może być sekwencją lub zawierać sekwencję. Na przykład źródło danych może być `IEnumerable<Student>` obiektem, gdzie każdy student w sekwencji zawiera listę wyników testu. Aby uzyskać dostęp do listy wewnętrznej w ramach każdego `Student` elementu, można użyć `from` klauzul złożonych. Technika przypomina użycie zagnieżdżonych instrukcji [foreach](foreach-in.md) . Można dodać klauzule [WHERE](partial-method.md) lub [OrderBy](orderby-clause.md) do obu `from` klauzul, aby przefiltrować wyniki. Poniższy przykład pokazuje sekwencję `Student` obiektów, z których każdy zawiera wewnętrzną `List` liczbę całkowitą reprezentującą wyniki testów. Aby uzyskać dostęp do listy wewnętrznej, użyj `from` klauzuli złożonej. W razie potrzeby można wstawiać klauzule między tymi dwiema `from` klauzulami.

[!code-csharp[cscsrefQueryKeywords#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/From.cs#2)]

## <a name="using-multiple-from-clauses-to-perform-joins"></a>Używanie wielu klauzul from do wykonywania sprzężeń

Klauzula złożona służy `from` do uzyskiwania dostępu do kolekcji wewnętrznych w jednym źródle danych. Jednak zapytanie może również zawierać wiele `from` klauzul, które generują dodatkowe zapytania z niezależnych źródeł danych. Ta technika umożliwia wykonywanie pewnych typów operacji JOIN, które nie są możliwe za pomocą [klauzuli join](join-clause.md).

Poniższy przykład pokazuje, jak dwie `from` klauzule mogą być używane do tworzenia pełnego sprzężenia krzyżowego dwóch źródeł danych.

[!code-csharp[cscsrefQueryKeywords#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/From.cs#3)]

Aby uzyskać więcej informacji na temat operacji łączenia, które korzystają z wielu `from` klauzul, zobacz [przełączenie do lewego sprzężenia zewnętrznego](../../linq/perform-left-outer-joins.md).

## <a name="see-also"></a>Zobacz też

- [Słowa kluczowe zapytania (LINQ)](query-keywords.md)
- [Language Integrated Query (LINQ)](../../linq/index.md)
