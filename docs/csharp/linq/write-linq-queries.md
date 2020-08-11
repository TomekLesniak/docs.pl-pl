---
title: Zapisywanie zapytań LINQ w C#
description: Dowiedz się, jak pisać zapytania LINQ w języku C#.
ms.date: 12/01/2016
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
ms.openlocfilehash: bd7da81f2873c6a25570cab32fafecc66fd98be4
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063448"
---
# <a name="write-linq-queries-in-c"></a>Zapisz zapytania LINQ w języku C\#

W tym artykule przedstawiono trzy sposoby pisania zapytania LINQ w języku C#:

1. Użyj składni zapytania.

2. Użyj składni metody.

3. Użyj kombinacji składni zapytania i składni metody.

W poniższych przykładach przedstawiono niektóre proste zapytania LINQ przy użyciu każdego z wymienionych wcześniej metod. Ogólnie rzecz biorąc, reguła jest używana (1) zawsze, gdy jest to możliwe, i w razie potrzeby używa (2) i (3).

> [!NOTE]
> Te zapytania działają w prostych kolekcjach w pamięci; Jednak podstawowa składnia jest taka sama jak używana w LINQ to Entities i LINQ to XML.

## <a name="example---query-syntax"></a>Przykład — Składnia zapytania

Zalecanym sposobem zapisu większości zapytań jest użycie *składni zapytań* w celu utworzenia *wyrażeń zapytania*. Poniższy przykład pokazuje trzy wyrażenia zapytania. Pierwsze wyrażenie zapytania pokazuje, jak filtrować lub ograniczać wyniki, stosując warunki z `where` klauzulą. Zwraca wszystkie elementy w sekwencji źródłowej, których wartości są większe niż 7 lub mniejsze niż 3. Drugie wyrażenie ilustruje sposób uporządkowania zwracanych wyników. Trzecie wyrażenie ilustruje sposób grupowania wyników według klucza. To zapytanie zwraca dwie grupy w oparciu o pierwszą literę wyrazu.

[!code-csharp[csProgGuideLINQ#5](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]

Należy pamiętać, że typ zapytań to <xref:System.Collections.Generic.IEnumerable%601> . Wszystkie te zapytania można napisać przy użyciu `var` , jak pokazano w następującym przykładzie:

`var query = from num in numbers...`

W każdym poprzednim przykładzie zapytania nie są wykonywane, dopóki nie zostanie wykonana iteracja zmiennej zapytania w `foreach` instrukcji lub innej instrukcji. Aby uzyskać więcej informacji, zobacz [wprowadzenie do zapytań LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).

## <a name="example---method-syntax"></a>Przykład — składnia metody

Niektóre operacje zapytań muszą być wyrażone jako wywołanie metody. Najbardziej powszechnymi metodami są te, które zwracają pojedyncze wartości liczbowe, takie jak,,, <xref:System.Linq.Enumerable.Sum%2A> <xref:System.Linq.Enumerable.Max%2A> <xref:System.Linq.Enumerable.Min%2A> <xref:System.Linq.Enumerable.Average%2A> i tak dalej. Te metody muszą zawsze być wywoływane jako ostatnie w dowolnych zapytaniach, ponieważ reprezentują tylko jedną wartość i nie mogą służyć jako źródło dodatkowej operacji zapytania. W poniższym przykładzie pokazano wywołanie metody w wyrażeniu zapytania:

[!code-csharp[csProgGuideLINQ#6](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]

Jeśli metoda zawiera parametry akcji lub Func, są one dostępne w formie wyrażenia [lambda](../language-reference/operators/lambda-expressions.md) , jak pokazano w następującym przykładzie:

[!code-csharp[csProgGuideLINQ#7](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]

W poprzednich zapytaniach tylko #4 zapytań są wykonywane. Dzieje się tak, ponieważ zwraca pojedynczą wartość, a nie ogólną <xref:System.Collections.Generic.IEnumerable%601> kolekcję. Aby `foreach` można było obliczyć jego wartość, należy użyć samej metody.

Wszystkie poprzednie zapytania można napisać przy użyciu niejawnego wpisywania z [var](../language-reference/keywords/var.md), jak pokazano w następującym przykładzie:

[!code-csharp[csProgGuideLINQ#8](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]

## <a name="example---mixed-query-and-method-syntax"></a>Przykład — mieszane składnie zapytań i metod

Ten przykład pokazuje, jak używać składni metody na wynikach klauzuli zapytania. Po prostu umieść wyrażenie zapytania w nawiasach, a następnie Zastosuj operator kropki i Wywołaj metodę. W poniższym przykładzie zapytanie #7 zwraca liczbę liczb, których wartość należy do zakresu od 3 do 7. Ogólnie rzecz biorąc, lepiej jest użyć drugiej zmiennej do przechowywania wyniku wywołania metody. W ten sposób zapytanie jest mniej podobne do wyników zapytania.

[!code-csharp[csProgGuideLINQ#9](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]

Ponieważ zapytanie #7 zwraca pojedynczą wartość, a nie kolekcję, zapytanie jest wykonywane natychmiast.

Poprzednie zapytanie można napisać przy użyciu niejawnego wpisywania w `var` , w następujący sposób:

```csharp
var numCount = (from num in numbers...
```

Można je napisać w składni metody w następujący sposób:

```csharp
var numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

Można ją napisać przy użyciu jawnego wpisywania w następujący sposób:

```csharp
int numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

## <a name="see-also"></a>Zobacz także

- [Przewodnik: Pisanie zapytań w języku C #](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)
- [Language Integrated Query (LINQ)](index.md)
- [Klauzula where](../language-reference/keywords/where-clause.md)
