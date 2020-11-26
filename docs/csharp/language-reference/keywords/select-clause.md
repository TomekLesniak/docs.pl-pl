---
description: SELECT — odwołanie w C#
title: SELECT — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- select_CSharpKeyword
- select
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
ms.openlocfilehash: d67c99cc841c08a63cc83843a07a46e80199b9d1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "89136905"
---
# <a name="select-clause-c-reference"></a>select — Klauzula (odwołanie w C#)

W wyrażeniu zapytania `select` klauzula określa typ wartości, które zostaną utworzone podczas wykonywania zapytania. Wynik jest oparty na ocenie wszystkich poprzednich klauzul i w dowolnych wyrażeniach w `select` samej klauzuli. Wyrażenie zapytania musi kończyć się `select` klauzulą lub [grupą](group-clause.md) .

Poniższy przykład pokazuje prostą `select` klauzulę w wyrażeniu zapytania.

[!code-csharp[cscsrefQueryKeywords#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#8)]  

Typ sekwencji utworzonej przez `select` klauzulę określa typ zmiennej zapytania `queryHighScores` . W najprostszym przypadku `select` klauzula określa tylko zmienną zakresu. Powoduje to, że zwracana sekwencja zawiera elementy tego samego typu co źródło danych. Aby uzyskać więcej informacji, zobacz temat [relacje typu w operacjach zapytań LINQ](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md). Jednak `select` klauzula zawiera również zaawansowany mechanizm przekształcania (lub *projekcji*) danych źródłowych na nowe typy. Aby uzyskać więcej informacji, zobacz [Przekształcanie danych za pomocą LINQ (C#)](../../programming-guide/concepts/linq/data-transformations-with-linq.md).

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano wszystkie różne formy, które `select` mogą wykonać klauzula. W każdym zapytaniu Zwróć uwagę na relacje między `select` klauzulą i typem *zmiennej zapytania* ( `studentQuery1` , `studentQuery2` itd.).

[!code-csharp[cscsrefQueryKeywords#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#9)]

Jak pokazano w `studentQuery8` poprzednim przykładzie, czasami warto chcieć, aby elementy zwracanej sekwencji zawierały tylko podzestaw właściwości elementów źródłowych. Przez pozostawienie zwróconej sekwencji jak najmniejszej ilości, można zmniejszyć wymagania dotyczące pamięci i zwiększyć szybkość wykonywania zapytania. Można to zrobić przez utworzenie typu anonimowego w `select` klauzuli i użycie inicjatora obiektów w celu zainicjowania go z odpowiednimi właściwościami z elementu źródłowego. Aby uzyskać przykład, jak to zrobić, zobacz [Inicjatory obiektów i kolekcji](../../programming-guide/classes-and-structs/object-and-collection-initializers.md).

## <a name="remarks"></a>Uwagi

W czasie kompilacji `select` klauzula jest tłumaczona na wywołanie metody do <xref:System.Linq.Enumerable.Select%2A> standardowego operatora zapytań.

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Słowa kluczowe zapytania (LINQ)](query-keywords.md)
- [Klauzula From](from-clause.md)
- [częściowe (Metoda) (odwołanie w C#)](partial-method.md)
- [Typy anonimowe](../../programming-guide/classes-and-structs/anonymous-types.md)
- [LINQ w C#](../../linq/index.md)
- [Language Integrated Query (LINQ)](../../programming-guide/concepts/linq/index.md)
