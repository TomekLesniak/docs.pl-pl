---
title: var — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: d944cde932b5c1f5ef1439ee46a1447e107e6ac9
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053078"
---
# <a name="var-c-reference"></a>var (odwołanie w C#)

Począwszy od języka Visual C# 3,0, zmienne, które są zadeklarowane w zakresie metody, mogą mieć niejawny typ "Type" `var` . Niejawnie wpisana zmienna lokalna jest silnie wpisana, tak jakby zadeklarowano typ samodzielnie, ale kompilator określa typ. Następujące dwie deklaracje `i` są funkcjonalnie równoważne:

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

Aby uzyskać więcej informacji, zobacz [niejawnie wpisane zmienne lokalne](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) i [relacje typu w operacjach zapytań LINQ](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).

> [!IMPORTANT]
> Gdy `var` jest używany z włączonymi typami odwołań dopuszczających wartość null, zawsze implikuje typ referencyjny dopuszczający wartość null, nawet jeśli typ wyrażenia nie dopuszcza wartości null.

## <a name="example"></a>Przykład

Poniższy przykład przedstawia dwa wyrażenia zapytania. W pierwszym wyrażeniu użycie `var` jest dozwolone, ale nie jest wymagane, ponieważ typ wyniku zapytania może być jawnie określony jako `IEnumerable<string>` . Jednak w drugim wyrażeniu, `var` umożliwia wynik jako Kolekcja typów anonimowych, a nazwa tego typu jest niedostępna z wyjątkiem kompilatora. Użycie `var` eliminuje wymóg tworzenia nowej klasy dla wyniku. Należy zauważyć, że w przykładzie #2 `foreach` Zmienna iteracji `item` również musi być wpisana niejawnie.

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Jawnie wpisana zmienna lokalna](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
