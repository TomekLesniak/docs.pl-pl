---
description: '?: operator-Dokumentacja języka C#'
title: '?: operator-Dokumentacja języka C#'
ms.date: 09/17/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: b6add045983619169bed0cd9f32eb27dba0a0338
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738882"
---
# <a name="-operator-c-reference"></a>?: — operator (odwołanie w C#)

Operator warunkowy `?:` , znany również jako operator warunkowy Trzyelementowy, oblicza wyrażenie logiczne i zwraca wynik jednego z dwóch wyrażeń, w zależności od tego, czy wyrażenie logiczne oblicza wartość `true` lub `false` .

Składnia operatora warunkowego jest następująca:

```csharp
condition ? consequent : alternative
```

`condition`Wyrażenie musi być szacowane do `true` lub `false` . Jeśli `condition` jest wynikiem obliczenia `true` , `consequent` wyrażenie jest oceniane, a jego wynik zmieni się na wynik operacji. Jeśli `condition` jest wynikiem obliczenia `false` , `alternative` wyrażenie jest oceniane, a jego wynik zmieni się na wynik operacji. Tylko `consequent` lub `alternative` jest oceniane.

Począwszy od języka C# 9,0, wyrażenia warunkowe mają typ docelowy. Oznacza to, że jeśli jest znany typ docelowy wyrażenia warunkowego, typy `consequent` i `alternative` muszą być niejawnie konwertowane na typ docelowy, jak pokazano na poniższym przykładzie:

[!code-csharp[target-typed conditional](snippets/shared/ConditionalOperator.cs#TargetTyped)]

Jeśli typ docelowy wyrażenia warunkowego jest nieznany (na przykład w przypadku użycia [`var`](../keywords/var.md) słowa kluczowego) lub w języku C# 8,0 i starszych, typ `consequent` i `alternative` musi być taki sam lub musi być niejawną konwersją z jednego typu na drugi:

[!code-csharp[not target-typed conditional](snippets/shared/ConditionalOperator.cs#NotTargetTyped)]

Operator warunkowy jest prawym przyciskiem asocjacyjnym, czyli wyrażeniem formularza

```csharp
a ? b : c ? d : e
```

jest oceniane jako

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> Poniższego urządzenia można użyć do zapamiętania, jak jest oceniany operator warunkowy:
>
> ```text
> is this condition true ? yes : no
> ```

Poniższy przykład ilustruje użycie operatora warunkowego:

[!code-csharp-interactive[non ref conditional](snippets/shared/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a>Wyrażenie warunkowe ref

Począwszy od języka C# 7,2, [lokalna](../keywords/ref.md#ref-locals) zmienna lokalna lub [ref tylko do odczytu](../keywords/ref.md#ref-readonly-locals) można przypisać warunkowo warunkowo wyrażenie ref. Można również użyć wyrażenia ref warunkowego jako [wartości zwracanej przez odwołanie](../keywords/ref.md#reference-return-values) lub jako [ `ref` argumentu metody](../keywords/ref.md#passing-an-argument-by-reference).

Składnia wyrażenia ref warunkowego jest następująca:

```csharp
condition ? ref consequent : ref alternative
```

Podobnie jak w przypadku oryginalnego operatora warunkowego wyrażenie ref oblicza tylko jedno z dwóch wyrażeń: albo `consequent` lub `alternative` .

W przypadku warunkowego wyrażenia ref typ `consequent` i `alternative` musi być taki sam. Wyrażenia referencyjne warunkowe nie są typami docelowymi.

Poniższy przykład demonstruje użycie warunkowego wyrażenia ref:

[!code-csharp-interactive[conditional ref](snippets/shared/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a>Operator warunkowy i `if..else` instrukcja

Użycie operatora warunkowego zamiast instrukcji [if-else](../keywords/if-else.md) może spowodować bardziej zwięzły kod w przypadkach, gdy konieczne jest warunkowe obliczenie wartości. Poniższy przykład ilustruje dwa sposoby klasyfikowania liczby całkowitej jako ujemnej lub nieujemnej:

[!code-csharp[conditional and if-else](snippets/shared/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a>Przeciążanie operatora

Typ zdefiniowany przez użytkownika nie może przeciążać operatora warunkowego.

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [warunkowego operatora](~/_csharplang/spec/expressions.md#conditional-operator) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

Aby uzyskać więcej informacji na temat funkcji dodanych w języku C# 7,2 i nowszych, zobacz następujące uwagi dotyczące propozycji funkcji:

- [Warunkowe wyrażenia ref (C# 7,2)](~/_csharplang/proposals/csharp-7.2/conditional-ref.md)
- [Wyrażenie warunkowe o typie docelowym (C# 9,0)](~/_csharplang/proposals/csharp-9.0/target-typed-conditional-expression.md)

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
- [if-else, instrukcja](../keywords/if-else.md)
- [?. lub? operator []](member-access-operators.md#null-conditional-operators--and-)
- [?? i? = — Operatory](null-coalescing-operator.md)
- [ref — słowo kluczowe](../keywords/ref.md)
