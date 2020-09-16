---
title: Wykonywanie sprzężeń zgrupowanych (LINQ w języku C#)
description: Dowiedz się, jak wykonywać zgrupowane sprzężenia przy użyciu LINQ w języku C#.
ms.date: 04/22/2020
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
ms.openlocfilehash: 6411479c5fe6cb0ee79a0cd3df6de2f4d42c26a2
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542812"
---
# <a name="perform-grouped-joins"></a>Wykonywanie sprzężeń grupowanych

Przyłączanie do grupy jest przydatne do tworzenia hierarchicznych struktur danych. Parowanie każdego elementu z pierwszej kolekcji z zestawem skorelowanych elementów z drugiej kolekcji.

Na przykład Klasa lub tabela relacyjnej bazy danych o nazwie `Student` mogą zawierać dwa pola: `Id` i `Name` . Druga klasa lub relacyjna tabela bazy danych o nazwie `Course` może zawierać dwa pola: `StudentId` i `CourseTitle` . Przyłączanie do grupy tych dwóch źródeł danych na podstawie zgodności `Student.Id` i `Course.StudentId` , grupuje każdy `Student` z kolekcją `Course` obiektów (może być pusta).

> [!NOTE]
> Każdy element pierwszej kolekcji pojawia się w zestawie wyników sprzężenia grupy, niezależnie od tego, czy skorelowane elementy znajdują się w drugiej kolekcji. W przypadku, gdy nie zostaną znalezione żadne skorelowane elementy, sekwencja skorelowanych elementów dla tego elementu jest pusta. Dlatego selektor wyniku ma dostęp do każdego elementu pierwszej kolekcji. Różni się to od selektora wyników w sprzężeniu innym niż grupa, które nie może uzyskać dostępu do elementów z pierwszej kolekcji, która nie ma dopasowania w drugiej kolekcji.

> [!WARNING]
> <xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType> nie ma bezpośredniego odpowiednika w tradycyjnych warunkach relacyjnej bazy danych. Jednakże ta metoda implementuje nadzbiór sprzężeń wewnętrznych i Lewe sprzężenia zewnętrzne. Obie te operacje można napisać w odniesieniu do zgrupowanego sprzężenia. Aby uzyskać więcej informacji, zobacz [operacje Join](../programming-guide/concepts/linq/join-operations.md) i [Entity Framework Core, GroupJoin —](/ef/core/querying/complex-query-operators#groupjoin).

Pierwszy przykład w tym artykule pokazuje, jak wykonać sprzężenie grupy. Drugi przykład pokazuje, jak używać sprzężenia grupy do tworzenia elementów XML.

## <a name="example---group-join"></a>Przykład — Dołącz do grupy

Poniższy przykład wykonuje przyłączanie do grupy obiektów typu `Person` i `Pet` w oparciu o `Person` pasującą `Pet.Owner` Właściwość. W przeciwieństwie do przyłączenia nienależących do grupy, która może utworzyć parę elementów dla każdego dopasowania, sprzężenie grupy generuje tylko jeden wynikowy obiekt dla każdego elementu pierwszej kolekcji, który w tym przykładzie jest `Person` obiektem. Odpowiednie elementy z drugiej kolekcji, w tym przykładzie są `Pet` obiektami, są pogrupowane w kolekcji. Na koniec funkcja selektora wyników tworzy typ anonimowy dla każdego dopasowania, które składa się z `Person.FirstName` i kolekcji `Pet` obiektów.

[!code-csharp[CsLINQProgJoining#5](~/samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]

## <a name="example---group-join-to-create-xml"></a>Przykład — przyłączenie do grupy w celu utworzenia pliku XML

Sprzężenia grup doskonale nadają się do tworzenia kodu XML przy użyciu LINQ to XML. Poniższy przykład jest podobny do poprzedniego przykładu, z wyjątkiem tego, że zamiast tworzenia typów anonimowych funkcja selektora wyników tworzy elementy XML, które reprezentują połączone obiekty.

[!code-csharp[CsLINQProgJoining#6](~/samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]

## <a name="see-also"></a>Zobacz także

- <xref:System.Linq.Enumerable.Join%2A>
- <xref:System.Linq.Enumerable.GroupJoin%2A>
- [Wykonywanie sprzężeń wewnętrznych](perform-inner-joins.md)
- [Wykonywanie lewych sprzężeń zewnętrznych](perform-left-outer-joins.md)
- [Typy anonimowe](../programming-guide/classes-and-structs/anonymous-types.md)
