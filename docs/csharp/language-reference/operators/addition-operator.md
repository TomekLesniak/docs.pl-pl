---
title: + Operatory and + = — odwołanie w C#
ms.date: 04/23/2020
f1_keywords:
- +_CSharpKeyword
- +=_CSharpKeyword
helpviewer_keywords:
- addition operator [C#]
- concatenation operator [C#]
- delegate combination [C#]
- + operator [C#]
- addition assignment operator [C#]
- event subscription [C#]
- += operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: f1db0054ad2411bfe23f10b64bc2727a71ad7463
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916949"
---
# <a name="-and--operators-c-reference"></a>Operatory + i + = (odwołanie w C#)

`+`Operatory i `+=` są obsługiwane przez wbudowane typy liczbowe [całkowite](../builtin-types/integral-numeric-types.md) i [zmiennoprzecinkowe](../builtin-types/floating-point-numeric-types.md) , typ [ciągu](../builtin-types/reference-types.md#the-string-type) i typy [delegatów](../builtin-types/reference-types.md#the-delegate-type) .

Aby uzyskać informacje o `+` operatorze arytmetycznym, zobacz [operatory jednoargumentowe Plus i minus](arithmetic-operators.md#unary-plus-and-minus-operators) oraz [operator dodawania +](arithmetic-operators.md#addition-operator-) sekcje w artykule [Operatory arytmetyczne](arithmetic-operators.md) .

## <a name="string-concatenation"></a>Łączenie ciągów

Gdy jeden lub oba operandy są typu [String](../builtin-types/reference-types.md#the-string-type), `+` operator łączy reprezentacje ciągów argumentów operacji (ciąg reprezentacja `null` jest ciągiem pustym):

[!code-csharp-interactive[string concatenation](snippets/shared/AdditionOperator.cs#AddStrings)]

Począwszy od języka C# 6, [Interpolacja ciągów](../tokens/interpolated.md) zapewnia wygodniejszy sposób formatowania ciągów:

[!code-csharp-interactive[string interpolation](snippets/shared/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a>Połączenie delegata

W przypadku operandów tego samego typu [delegata](../builtin-types/reference-types.md#the-delegate-type) `+` operator zwraca nowe wystąpienie delegata, które po wywołaniu wywołuje argument operacji po lewej stronie, a następnie wywołuje operand z prawej strony. Jeśli którykolwiek z operandów jest `null` , `+` operator zwraca wartość innego operandu (co również może być `null` ). Poniższy przykład pokazuje, jak można łączyć delegatów z `+` operatorem:

[!code-csharp-interactive[delegate combination](snippets/shared/AdditionOperator.cs#AddDelegates)]

Aby przeprowadzić usuwanie delegata, użyj [ `-` operatora](subtraction-operator.md#delegate-removal).

Aby uzyskać więcej informacji na temat typów delegatów, zobacz [delegats](../../programming-guide/delegates/index.md).

## <a name="addition-assignment-operator-"></a>Operator przypisania dodawania + =

Wyrażenie używające `+=` operatora, takie jak

```csharp
x += y
```

jest równoważny

```csharp
x = x + y
```

z tą różnicą, że `x` jest obliczana tylko raz.

Poniższy przykład ilustruje użycie `+=` operatora:

[!code-csharp-interactive[+= examples](snippets/shared/AdditionOperator.cs#AddAndAssign)]

Możesz również użyć `+=` operatora, aby określić metodę procedury obsługi zdarzeń podczas subskrybowania [zdarzenia](../keywords/event.md). Aby uzyskać więcej informacji, zobacz [How to: subskrybowanie i anulowanie subskrypcji zdarzeń](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-overloadability"></a>Przeciążanie operatora

Typ zdefiniowany przez użytkownika może [przeciążać](operator-overloading.md) `+` operatora. Gdy operator binarny `+` jest przeciążony, `+=` operator jest również niejawnie przeciążony. Typ zdefiniowany przez użytkownika nie może jawnie przeciążać `+=` operatora.

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz sekcje [jednoargumentowe Plus](~/_csharplang/spec/expressions.md#unary-plus-operator) i [operator dodawania](~/_csharplang/spec/expressions.md#addition-operator) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
- [Jak połączyć wiele ciągów](../../how-to/concatenate-multiple-strings.md)
- [Zdarzenia](../../programming-guide/events/index.md)
- [Operatory arytmetyczne](arithmetic-operators.md)
- [Operatory-and-=](subtraction-operator.md)
