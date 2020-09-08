---
title: Operatory bitowe i przesunięcia — odwołanie w C#
description: Informacje na temat operatorów języka C#, które wykonują bitowe operacje logiczne lub przesunięcia przy użyciu operandów typów całkowitych.
ms.date: 04/18/2019
author: pkulikov
f1_keywords:
- ~_CSharpKeyword
- <<_CSharpKeyword
- '>>_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- <<=_CSharpKeyword
- '>>=_CSharpKeyword'
helpviewer_keywords:
- bitwise logical operators [C#]
- shift operators [C#]
- tilde operator [C#]
- one's complement operator [C#]
- bitwise complement operator [C#]
- ~ operator [C#]
- left shift operator [C#]
- << operator [C#]
- right shift operator [C#]
- '>> operator [C#]'
- bitwise logical AND operator [C#]
- ampersand operator [C#]
- '& operator [C#]'
- bitwise logical exclusive OR operator [C#]
- bitwise logical XOR operator [C#]
- ^ operator [C#]
- bitwise logical OR operator [C#]
- '| operator [C#]'
ms.openlocfilehash: 061abc8bc37d166a3683be1d2ad920a083a8ea3b
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89515946"
---
# <a name="bitwise-and-shift-operators-c-reference"></a>Operatory bitowe i przesunięcia (odwołanie w C#)

Następujące operatory wykonują operacje bitowe lub przesunięcia przy użyciu operandów [całkowitych typów liczbowych](../builtin-types/integral-numeric-types.md) lub typu [char](../builtin-types/char.md) :

- Operator jednoargumentowy (dopełnienie [ `~` bitowe)](#bitwise-complement-operator-)
- Operatory przesunięcia binarnego (przesunięcie w [ `<<` lewo)](#left-shift-operator-) i [ `>>` (prawy shift)](#right-shift-operator-)
- Operatory binarne [ `&` (logiczne i)](#logical-and-operator-), [ `|` (logiczne lub)](#logical-or-operator-)i [ `^` (logiczne wyłączne OR)](#logical-exclusive-or-operator-)

Te operatory są zdefiniowane dla `int` typów, `uint` , `long` i `ulong` . Gdy oba operandy są innymi typami całkowitymi ( `sbyte` , `byte` , `short` , `ushort` lub `char` ), ich wartości są konwertowane na `int` Typ, który jest również typem wyniku operacji. Gdy operandy są różnymi typami całkowitymi, ich wartości są konwertowane na najbliższy typ całkowity. Aby uzyskać więcej informacji, zobacz sekcję [promocje liczbowe](~/_csharplang/spec/expressions.md#numeric-promotions) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).

`&`Operatory, `|` i `^` są również zdefiniowane dla argumentów operacji `bool` typu. Aby uzyskać więcej informacji, zobacz logiczne [Operatory logiczne](boolean-logical-operators.md).

Operacje bitowe i przesunięcia nigdy nie powodują przepełnienia i tworzą te same wyniki w kontekstach [zaewidencjonowanych i](../keywords/checked-and-unchecked.md) niezaznaczone.

## <a name="bitwise-complement-operator-"></a>Operator uzupełnienia bitowego ~

`~`Operator generuje koniunkcję bitową operandu przez odwrócenie każdego bitu:

[!code-csharp-interactive[bitwise NOT](snippets/shared/BitwiseAndShiftOperators.cs#BitwiseComplement)]

Możesz również użyć symbolu, `~` Aby zadeklarować finalizatory. Aby uzyskać więcej informacji, zobacz [finalizatory](../../programming-guide/classes-and-structs/destructors.md).

## <a name="left-shift-operator-"></a>Operator przesunięcia w lewo \<\<

`<<`Operator przesuwa swój lewy argument operacji pozostawiony przez [liczbę bitów zdefiniowanych przez swój operand z prawej strony](#shift-count-of-the-shift-operators).

Operacja przesunięcia w lewo odrzuca bity o wysokim stopniu, które znajdują się poza zakresem wyników, i ustawia puste pozycje bitu w porządku o wartości zero, jak pokazano w poniższym przykładzie:

[!code-csharp-interactive[left shift](snippets/shared/BitwiseAndShiftOperators.cs#LeftShift)]

Ponieważ operatory przesunięcia są zdefiniowane tylko dla `int` typów, `uint` , `long` i `ulong` , wynik operacji zawsze zawiera co najmniej 32 bitów. Jeśli argument operacji po lewej stronie jest innego typu całkowitego ( `sbyte` , `byte` ,, `short` `ushort` lub `char` ), jego wartość jest konwertowana na `int` Typ, jak pokazano na poniższym przykładzie:

[!code-csharp-interactive[left shift with promotion](snippets/shared/BitwiseAndShiftOperators.cs#LeftShiftPromoted)]

Aby uzyskać informacje o tym, jak argument operacji po prawej stronie `<<` operatora definiuje liczbę przesunięć, zobacz [Liczba przesunięć w sekcji operatory przesunięcia](#shift-count-of-the-shift-operators) .

## <a name="right-shift-operator-"></a>Operator przesunięcia w prawo >>

`>>`Operator przesuwa swój lewy argument operacji bezpośrednio przez [liczbę bitów zdefiniowanych przez jego operand po prawej stronie](#shift-count-of-the-shift-operators).

Operacja przesunięcia w prawo powoduje odrzucenie bitów o niskiej kolejności, jak pokazano w poniższym przykładzie:

[!code-csharp-interactive[right shift](snippets/shared/BitwiseAndShiftOperators.cs#RightShift)]

Puste pozycje w dużej kolejności są ustawiane na podstawie typu operandu po lewej stronie w następujący sposób:

- Jeśli argument operacji po lewej stronie jest typu `int` lub `long` , operator przesunięcia w prawo wykonuje *arytmetyczne* przesunięcie: wartość najbardziej znaczącego bitu (bit znaku) operandu po lewej stronie jest propagowana do pustych pozycji w dużej kolejności. Oznacza to, że puste pozycje bitu o wysokim stopniu kolejności są ustawione na zero, jeśli argument operacji po lewej stronie jest nieujemny i ustawiony na jeden, jeśli jest ujemny.

  [!code-csharp-interactive[arithmetic right shift](snippets/shared/BitwiseAndShiftOperators.cs#ArithmeticRightShift)]

- Jeśli argument operacji po lewej stronie jest typu `uint` lub `ulong` , operator przesunięcia w prawo wykonuje *logiczne* przesunięcie: wartość pustych pozycji w dużej kolejności jest zawsze ustawiana na zero.

  [!code-csharp-interactive[logical right shift](snippets/shared/BitwiseAndShiftOperators.cs#LogicalRightShift)]

Aby uzyskać informacje o tym, jak argument operacji po prawej stronie `>>` operatora definiuje liczbę przesunięć, zobacz [Liczba przesunięć w sekcji operatory przesunięcia](#shift-count-of-the-shift-operators) .

## <a name="logical-and-operator-amp"></a><a name="logical-and-operator-"></a> Operator logiczny AND &amp;

`&`Operator oblicza koniunkcję bitową i jej całkowite operandy:

[!code-csharp-interactive[bitwise AND](snippets/shared/BitwiseAndShiftOperators.cs#BitwiseAnd)]

Dla `bool` operandów `&` operator oblicza wartość [logiczną i](boolean-logical-operators.md#logical-and-operator-) jej operandów. Operator jednoargumentowy jest operatorem `&` [Address-of](pointer-related-operators.md#address-of-operator-).

## <a name="logical-exclusive-or-operator-"></a>Operator wyłączny logicznego OR ^

Operator oblicza bitową koniunkcję niezależną `^` lub, znaną również jako bitowe koniunkcje logiczne XOR, z całkowitymi operandami:

[!code-csharp-interactive[bitwise XOR](snippets/shared/BitwiseAndShiftOperators.cs#BitwiseXor)]

W przypadku `bool` operandów `^` operator oblicza [logiczne wyłącznych lub](boolean-logical-operators.md#logical-exclusive-or-operator-) wartości operandów.

## <a name="logical-or-operator-"></a>Operator logiczny OR |

`|`Operator oblicza bitową koniunkcję logiczną lub jej całkowite operandy:

[!code-csharp-interactive[bitwise OR](snippets/shared/BitwiseAndShiftOperators.cs#BitwiseOr)]

Dla `bool` operandów `|` operator oblicza wartość [logiczną lub](boolean-logical-operators.md#logical-or-operator-) argumentów operacji.

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

Poniższy przykład ilustruje użycie przypisania złożonego z operatory bitowe i przesunięcia:

[!code-csharp-interactive[compound assignment](snippets/shared/BitwiseAndShiftOperators.cs#CompoundAssignment)]

Ze względu na [promocje liczbowe](~/_csharplang/spec/expressions.md#numeric-promotions)wynik `op` operacji może nie być niejawnie konwertowany na typ `T` `x` . W takim przypadku, jeśli `op` jest wstępnie zdefiniowanym operatorem, a wynik operacji jest jawnie konwertowany na typ `T` `x` , wyrażenie przypisania złożonego formularza `x op= y` jest równoważne z `x = (T)(x op y)` , z tą różnicą, że `x` jest tylko raz oceniane. Poniższy przykład ilustruje takie zachowanie:

[!code-csharp-interactive[compound assignment with cast](snippets/shared/BitwiseAndShiftOperators.cs#CompoundAssignmentWithCast)]

## <a name="operator-precedence"></a>Kolejność wykonywania działań

Poniższa lista porządkuje operatory bitowe i przesunięcia, rozpoczynając od najwyższego priorytetu do najniższego:

- Operator dopełnienia bitowego `~`
- Operatory przesunięcia `<<` i `>>`
- Operator logiczny AND `&`
- Operator wyłączny logicznego OR `^`
- Operator logiczny OR `|`

Użyj nawiasów, `()` Aby zmienić kolejność oceny nałożona przez pierwszeństwo operatorów:

[!code-csharp-interactive[operator precedence](snippets/shared/BitwiseAndShiftOperators.cs#Precedence)]

Aby uzyskać pełną listę operatorów języka C# uporządkowanych według poziomu pierwszeństwa, zobacz sekcję [pierwszeństwo](index.md#operator-precedence) operatorów w artykule [operatory języka c#](index.md) .

## <a name="shift-count-of-the-shift-operators"></a>Liczba przesunięć operatorów przesunięcia

Dla operatorów przesunięcia `<<` i `>>` typ operandu z prawej strony musi być `int` lub typem, który ma [wstępnie zdefiniowaną niejawną konwersję liczbową](../builtin-types/numeric-conversions.md#implicit-numeric-conversions) na `int` .

W przypadku `x << count` `x >> count` wyrażeń i rzeczywista liczba przesunięć zależy od typu w `x` następujący sposób:

- Jeśli typ `x` to `int` lub `uint` , liczba przesunięć jest definiowana przez *pięć* bitów z prawej strony. Oznacza to, że liczba przesunięć jest obliczana z `count & 0x1F` (lub `count & 0b_1_1111` ).

- Jeśli typ ma wartość `x` `long` lub `ulong` , liczba przesunięć jest definiowana przez *6* -znaczący bity operandu po prawej stronie. Oznacza to, że liczba przesunięć jest obliczana z `count & 0x3F` (lub `count & 0b_11_1111` ).

Poniższy przykład ilustruje takie zachowanie:

[!code-csharp-interactive[shift count example](snippets/shared/BitwiseAndShiftOperators.cs#ShiftCount)]

> [!NOTE]
> Jak pokazano w powyższym przykładzie, wynik operacji przesunięcia może być różny od zera, nawet jeśli wartość operandu po prawej stronie jest większa niż liczba bitów w lewym operandzie.

## <a name="enumeration-logical-operators"></a>Wyliczanie operatorów logicznych

`~`Operatory, `&` , `|` , i `^` są również obsługiwane przez dowolny typ [wyliczeniowy](../builtin-types/enum.md) . Dla operandów o tym samym typie wyliczeniowym operacja logiczna jest wykonywana na odpowiednich wartościach bazowego typu całkowitego. Na przykład dla dowolnego `x` i `y` typu wyliczenia `T` z typem podstawowym `U` `x & y` wyrażenie daje ten sam wynik co `(T)((U)x & (U)y)` wyrażenie.

Zwykle używane są bitowe operatory logiczne z typem wyliczenia, który jest zdefiniowany przy użyciu atrybutu [flags](xref:System.FlagsAttribute) . Aby uzyskać więcej informacji, zobacz sekcję [typy wyliczeniowe jako flagi bitowe](../builtin-types/enum.md#enumeration-types-as-bit-flags) artykułu [typy wyliczeniowe](../builtin-types/enum.md) .

## <a name="operator-overloadability"></a>Przeciążanie operatora

Typ zdefiniowany przez użytkownika może [przeciążać](operator-overloading.md) `~` operatory,,,, `<<` `>>` `&` `|` i `^` . Gdy operator binarny jest przeciążony, odpowiadający mu operator przypisania złożonego jest również niejawnie przeciążony. Typ zdefiniowany przez użytkownika nie może jawnie przeciążać złożonego operatora przypisania.

Jeśli typ zdefiniowany przez użytkownika `T` przeciążuje `<<` `>>` operator OR, typem operandu po lewej stronie musi być `T` i typem argumentu z prawej strony musi być `int` .

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz następujące sekcje [specyfikacji języka C#](~/_csharplang/spec/introduction.md):

- [Operator dopełnienia bitowego](~/_csharplang/spec/expressions.md#bitwise-complement-operator)
- [Operatory przesunięcia](~/_csharplang/spec/expressions.md#shift-operators)
- [Operatory logiczne](~/_csharplang/spec/expressions.md#logical-operators)
- [Przypisanie złożone](~/_csharplang/spec/expressions.md#compound-assignment)
- [Promocje numeryczne](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a>Zobacz też

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
- [Operatory logiczne (Boolean)](boolean-logical-operators.md)
