---
title: Operatory przypisania — odwołanie w C#
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 7b4f3b3f4d6b697903461f08435552f2df36bfe4
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916934"
---
# <a name="assignment-operators-c-reference"></a>Operatory przypisania (odwołanie w C#)

Operator przypisania `=` przypisuje wartość jego operandu po prawej stronie do zmiennej, [Właściwości](../../programming-guide/classes-and-structs/properties.md)lub elementu [indeksatora](../../programming-guide/indexers/index.md) podanym przez operand z lewej strony. Wynikiem wyrażenia przypisania jest wartość przypisana do operandu po lewej stronie. Typ operandu po prawej stronie musi być taki sam jak typ operandu po lewej stronie lub niejawnie konwertowany.

Operator przypisania `=` jest prawym przyciskiem asocjacyjnym, czyli wyrażeniem formularza

```csharp
a = b = c
```

jest oceniane jako

```csharp
a = (b = c)
```

Poniższy przykład ilustruje użycie operatora przypisania ze zmienną lokalną, właściwością i elementem indeksatora jako swój argument operacji po lewej stronie:

[!code-csharp-interactive[simple assignment](snippets/shared/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a>operator przypisania ref

Począwszy od języka C# 7,3, można użyć operatora przypisania odwołania, `= ref` Aby ponownie przypisać [lokalną](../keywords/ref.md#ref-locals) zmienną lokalną lub [ref tylko do odczytu](../keywords/ref.md#ref-readonly-locals) . Poniższy przykład ilustruje użycie operatora przypisania odwołania:

[!code-csharp[ref assignment operator](snippets/shared/AssignmentOperator.cs#RefAssignment)]

W przypadku operatora przypisania odwołania, oba operandy muszą być tego samego typu.

## <a name="compound-assignment"></a>Przypisanie złożone

Dla operatora binarnego `op` wyrażenie złożonego przypisania formularza

```csharp
x op= y
```

jest równoważny

```csharp
x = x op y
```

z tą różnicą, że `x` jest obliczana tylko raz.

Przypisanie złożone jest obsługiwane przez [arytmetyczne](arithmetic-operators.md#compound-assignment)operatory [logiczne logiczne](boolean-logical-operators.md#compound-assignment) [i bitowe](bitwise-and-shift-operators.md#compound-assignment) .

## <a name="null-coalescing-assignment"></a>Przypisanie do łączenia o wartości null

Począwszy od języka C# 8,0, można użyć operatora przypisania łączącego wartości null, `??=` Aby przypisać wartość jego operandu po lewej stronie tylko wtedy, gdy argument operacji po lewej stronie jest wynikiem `null` . Aby uzyskać więcej informacji, zobacz [? =](null-coalescing-operator.md) — artykuł.

## <a name="operator-overloadability"></a>Przeciążanie operatora

Typ zdefiniowany przez użytkownika nie może [przeciążać](operator-overloading.md) operatora przypisania. Jednak typ zdefiniowany przez użytkownika może definiować niejawną konwersję na inny typ. W ten sposób wartość typu zdefiniowanego przez użytkownika może być przypisana do zmiennej, właściwości lub elementu indeksatora innego typu. Aby uzyskać więcej informacji, zobacz [Operatory konwersji zdefiniowane przez użytkownika](user-defined-conversion-operators.md).

Typ zdefiniowany przez użytkownika nie może jawnie przeciążać złożonego operatora przypisania. Jeśli jednak typ zdefiniowany przez użytkownika przeciąża operator binarny, `op` `op=` operator (jeśli istnieje) jest również niejawnie przeciążony.

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcję [Operatory przypisania](~/_csharplang/spec/expressions.md#assignment-operators) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

Aby uzyskać więcej informacji na temat operatora przypisania odwołania `= ref` , zobacz [Uwaga dotycząca oferty funkcji](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
- [ref — słowo kluczowe](../keywords/ref.md)
