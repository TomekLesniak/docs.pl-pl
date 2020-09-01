---
description: '?: operator-Dokumentacja języka C#'
title: '?: operator-Dokumentacja języka C#'
ms.date: 03/06/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 0efa6de2b537fd3af76807938ac2b50a2716561f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122358"
---
# <a name="-operator-c-reference"></a>?: — operator (odwołanie w C#)

Operator warunkowy `?:` , znany również jako operator warunkowy Trzyelementowy, oblicza wyrażenie logiczne i zwraca wynik jednego z dwóch wyrażeń, w zależności od tego, czy wyrażenie logiczne oblicza wartość `true` lub `false` .

Składnia operatora warunkowego jest następująca:

```csharp
condition ? consequent : alternative
```

`condition`Wyrażenie musi być szacowane do `true` lub `false` . Jeśli `condition` jest wynikiem obliczenia `true` , `consequent` wyrażenie jest oceniane, a jego wynik zmieni się na wynik operacji. Jeśli `condition` jest wynikiem obliczenia `false` , `alternative` wyrażenie jest oceniane, a jego wynik zmieni się na wynik operacji. Tylko `consequent` lub `alternative` jest oceniane.

Typ `consequent` i `alternative` musi być taki sam lub musi być niejawną konwersją z jednego typu na drugi.

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

W przypadku warunkowego wyrażenia ref typ `consequent` i `alternative` musi być taki sam.

Poniższy przykład demonstruje użycie warunkowego wyrażenia ref:

[!code-csharp-interactive[conditional ref](snippets/shared/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a>Operator warunkowy i `if..else` instrukcja

Użycie operatora warunkowego zamiast instrukcji [if-else](../keywords/if-else.md) może spowodować bardziej zwięzły kod w przypadkach, gdy konieczne jest warunkowe obliczenie wartości. Poniższy przykład ilustruje dwa sposoby klasyfikowania liczby całkowitej jako ujemnej lub nieujemnej:

[!code-csharp[conditional and if-else](snippets/shared/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a>Przeciążanie operatora

Typ zdefiniowany przez użytkownika nie może przeciążać operatora warunkowego.

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [warunkowego operatora](~/_csharplang/spec/expressions.md#conditional-operator) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

Aby uzyskać więcej informacji na temat wyrażenia ref warunkowego, zobacz [Uwaga dotycząca oferty funkcji](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
- [if-else, instrukcja](../keywords/if-else.md)
- [?. lub? operator []](member-access-operators.md#null-conditional-operators--and-)
- [?? i? = — Operatory](null-coalescing-operator.md)
- [ref — słowo kluczowe](../keywords/ref.md)
