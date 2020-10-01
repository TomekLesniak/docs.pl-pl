---
description: var — odwołanie w C#
title: var — odwołanie w C#
ms.date: 10/02/2020
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: d04bea9bcf5be726d3e81a1a53abed31f59330a0
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608715"
---
# <a name="var-c-reference"></a>var (odwołanie w C#)

Począwszy od języka C# 3 zmienne, które są zadeklarowane w zakresie metody, mogą mieć niejawny typ "Type" `var` . Niejawnie wpisana zmienna lokalna jest silnie wpisana, tak jakby zadeklarowano typ samodzielnie, ale kompilator określa typ. Następujące dwie deklaracje `i` są funkcjonalnie równoważne:

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

> [!IMPORTANT]
> Gdy `var` jest używany z włączonymi [typami odwołań dopuszczających wartość null](../builtin-types/nullable-reference-types.md) , zawsze implikuje typ referencyjny dopuszczający wartość null, nawet jeśli typ wyrażenia nie dopuszcza wartości null.

Typowym zastosowaniem `var` słowa kluczowego jest wyrażenie wywołania konstruktora. Użycie programu `var` umożliwia nie powtarzanie nazwy typu w deklaracji zmiennej i tworzeniu wystąpienia obiektu, jak pokazano na poniższym przykładzie:

```csharp
var xs = new List<int>();
```

Począwszy od języka C# 9,0, można użyć [ `new` wyrażenia](../operators/new-operator.md) z typem docelowym jako alternatywy:

```csharp
List<int> xs = new();
List<int>? ys = new();
```

## <a name="example"></a>Przykład

Poniższy przykład przedstawia dwa wyrażenia zapytania. W pierwszym wyrażeniu użycie `var` jest dozwolone, ale nie jest wymagane, ponieważ typ wyniku zapytania może być jawnie określony jako `IEnumerable<string>` . Jednak w drugim wyrażeniu, `var` umożliwia wynik jako Kolekcja typów anonimowych, a nazwa tego typu jest niedostępna z wyjątkiem kompilatora. Użycie `var` eliminuje wymóg tworzenia nowej klasy dla wyniku. Należy zauważyć, że w przykładzie #2 `foreach` Zmienna iteracji `item` również musi być wpisana niejawnie.

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Niejawnie wpisane zmienne lokalne](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
- [Relacje typu w operacjach zapytań LINQ](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
