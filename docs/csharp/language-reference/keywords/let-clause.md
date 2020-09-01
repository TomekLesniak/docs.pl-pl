---
description: klauzula Let — odwołanie w C#
title: klauzula Let — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: 3767b9745cccd9802374a8100de19f286c9b55ea
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139596"
---
# <a name="let-clause-c-reference"></a>Klauzula Let (odwołanie w C#)

W wyrażeniu zapytania czasami warto przechowywać wynik wyrażenia podrzędnego w celu użycia go w kolejnych klauzulach. Można to zrobić za pomocą `let` słowa kluczowego, które tworzy nową zmienną zakresu i inicjuje ją z wynikiem podania wyrażenia. Po zainicjowaniu z wartością zmienna zakresu nie może być używana do przechowywania innej wartości. Jeśli jednak zmienna zakresu zawiera typ queryable, może to być zapytanie.

## <a name="example"></a>Przykład

W poniższym przykładzie `let` jest używany na dwa sposoby:

1. Aby utworzyć wyliczalny typ, który może być badany.

2. Aby włączyć wywoływanie zapytania `ToLower` tylko raz dla zmiennej zakresu `word` . Bez użycia `let` , należy wywołać `ToLower` każdy predykat w `where` klauzuli.

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Słowa kluczowe zapytania (LINQ)](query-keywords.md)
- [LINQ w C#](../../linq/index.md)
- [Language Integrated Query (LINQ)](../../programming-guide/concepts/linq/index.md)
- [Obsługa wyjątków w wyrażeniach zapytań](../../linq/handle-exceptions-in-query-expressions.md)
