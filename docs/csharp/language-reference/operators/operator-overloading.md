---
title: Przeciążanie operatora — odwołanie w C#
description: Dowiedz się, jak przeciążać operator języka C# i które operatory języka C# są przeciążone.
ms.date: 07/05/2019
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
- operator overloading [C#]
ms.openlocfilehash: 8b15d8d3abdfc9318baaba60ee0d6d1bb18fcf27
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855078"
---
# <a name="operator-overloading-c-reference"></a>Przeciążanie operatora (odwołanie w C#)

Typ zdefiniowany przez użytkownika może przeciążać wstępnie zdefiniowany operator języka C#. Oznacza to, że typ może zapewnić niestandardową implementację operacji w przypadku, gdy jeden lub oba operandy są tego typu. Sekcja [Operatory](#overloadable-operators) z możliwością przeciążenia pokazuje, które operatory języka C# mogą być przeciążone.

Użyj `operator` słowa kluczowego, aby zadeklarować operator. Deklaracja operatora musi spełniać następujące zasady:

- Zawiera `public` modyfikator a i `static` .
- Jednoargumentowy operator ma jeden parametr wejściowy. Operator binarny ma dwa parametry wejściowe. W każdym przypadku co najmniej jeden parametr musi mieć typ `T` lub `T?` gdzie `T` jest typem, który zawiera deklarację operatora.

Poniższy przykład definiuje uproszczoną strukturę do reprezentowania liczby wymiernej. Struktura przeciąża niektóre [Operatory arytmetyczne](arithmetic-operators.md):

[!code-csharp[fraction example](snippets/OperatorOverloading.cs)]

Możesz poszerzyć poprzedni przykład, [definiując niejawną konwersję](user-defined-conversion-operators.md) z `int` na `Fraction` . Następnie przeciążone operatory obsługują argumenty tych dwóch typów. Oznacza to, że można dodać liczbę całkowitą do ułamka i uzyskać ułamek jako wynik.

Możesz również użyć `operator` słowa kluczowego, aby zdefiniować niestandardową konwersję typu. Aby uzyskać więcej informacji, zobacz [Operatory konwersji zdefiniowane przez użytkownika](user-defined-conversion-operators.md).

## <a name="overloadable-operators"></a>Operatory z możliwością przeciążenia

Poniższa tabela zawiera informacje dotyczące przeciążania operatorów języka C#:

| Operatory | Przeciążenie |
| --------- | --------------- |
|[+ x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [! x](boolean-logical-operators.md#logical-negation-operator-), [~ x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++](arithmetic-operators.md#increment-operator-) , [--](arithmetic-operators.md#decrement-operator---) , [true](true-false-operators.md), [false](true-false-operators.md)|Te operatory jednoargumentowe mogą być przeciążone.|
|[x + y](addition-operator.md), [x-y](subtraction-operator.md), [x \* y](arithmetic-operators.md#multiplication-operator-), [x/y](arithmetic-operators.md#division-operator-), [x% y](arithmetic-operators.md#remainder-operator-), [x & y](boolean-logical-operators.md#logical-and-operator-), [x &#124; y](boolean-logical-operators.md#logical-or-operator-), [x ^ y](boolean-logical-operators.md#logical-exclusive-or-operator-), [x \<\< y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-), [x = = y](equality-operators.md#equality-operator-), [x! = y](equality-operators.md#inequality-operator-), [x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x = \<= y](comparison-operators.md#less-than-or-equal-operator-), [x > y](comparison-operators.md#greater-than-or-equal-operator-)|Te operatory binarne mogą być przeciążone. Niektóre operatory muszą być przeciążone w parach; Więcej informacji można znaleźć w poniższej tabeli.|
|[x && y](boolean-logical-operators.md#conditional-logical-and-operator-), [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-)|Warunkowe operatory logiczne nie mogą być przeciążone. Jednakże, jeśli typ ze przeciążonym [ `true` `false` operatorem i operatory](true-false-operators.md) przeciążą `&` <code>&#124;</code> operator OR w określony sposób, `&&` lub <code>&#124;&#124;</code> , odpowiednio, można obliczyć dla operandów tego typu. Aby uzyskać więcej informacji, zapoznaj się z sekcją wyrażenia [warunkowe operatory logiczne zdefiniowane przez użytkownika](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).|
|[&#91;i&#93;](member-access-operators.md#indexer-operator-),[`a?[i]`](member-access-operators.md#null-conditional-operators--and-)|Dostęp do elementu nie jest traktowany jako operator z możliwością przeciążenia, ale można zdefiniować [indeksator](../../programming-guide/indexers/index.md).|
|[(T) x](type-testing-and-cast.md#cast-expression)|Operator rzutowania nie może być przeciążony, ale można zdefiniować konwersje typu niestandardowego, które mogą być wykonywane przez wyrażenie rzutowania. Aby uzyskać więcej informacji, zobacz [Operatory konwersji zdefiniowane przez użytkownika](user-defined-conversion-operators.md).|
|[+=](arithmetic-operators.md#compound-assignment), [-=](arithmetic-operators.md#compound-assignment) ,,, [\*=](arithmetic-operators.md#compound-assignment) [/=](arithmetic-operators.md#compound-assignment) [%=](arithmetic-operators.md#compound-assignment) , [&=](boolean-logical-operators.md#compound-assignment) [&#124;=](boolean-logical-operators.md#compound-assignment), [^=](boolean-logical-operators.md#compound-assignment) ,[\<\<=](bitwise-and-shift-operators.md#compound-assignment), [>>=](bitwise-and-shift-operators.md#compound-assignment)|Operatory przypisania złożonego nie mogą być jawnie przeciążone. Jednak w przypadku przeciążenia operatora binarnego odpowiedni operator przypisania złożonego, jeśli istnieje, również jest niejawnie przeciążony. Na przykład, `+=` jest oceniane przy użyciu `+` , który może być przeciążony.|
|[^ x](member-access-operators.md#index-from-end-operator-), [x = y](assignment-operator.md), [x. y](member-access-operators.md#member-access-expression-), [`x?.y`](member-access-operators.md#null-conditional-operators--and-) , [c? t: f](conditional-operator.md), [x?? y](null-coalescing-operator.md), [x? = y](null-coalescing-operator.md), [x.. y](member-access-operators.md#range-operator-), [x->y](pointer-related-operators.md#pointer-member-access-operator--), [=>](lambda-operator.md) , [f (x)](member-access-operators.md#invocation-expression-), [as](type-testing-and-cast.md#as-operator), [await](await.md), [niezaznaczone](../keywords/checked.md), [niezaznaczone](../keywords/unchecked.md), [Domyślnie](default.md), [Delegat](delegate-operator.md), [is](type-testing-and-cast.md#is-operator), [nameof](nameof.md), [New](new-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [Switch](switch-expression.md), [typeof](type-testing-and-cast.md#typeof-operator)|Te operatory nie mogą być przeciążone.|

> [!NOTE]
> Operatory porównania muszą być przeciążone w parach. Oznacza to, że jeśli oba operatory pary są przeciążone, drugi operator musi być przeciążony. Takie pary są następujące:
>
> - `==``!=`Operatory i
> - `<``>`Operatory i
> - `<=``>=`Operatory i

## <a name="c-language-specification"></a>specyfikacja języka C#

Aby uzyskać więcej informacji, zobacz następujące sekcje [specyfikacji języka C#](~/_csharplang/spec/introduction.md):

- [Przeładowanie operatora](~/_csharplang/spec/expressions.md#operator-overloading)
- [Operatory](~/_csharplang/spec/classes.md#operators)

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Operatory i wyrażenia języka C#](index.md)
- [Operatory konwersji zdefiniowane przez użytkownika](user-defined-conversion-operators.md)
- [Wytyczne dotyczące projektowania — przeciążenia operatorów](../../../standard/design-guidelines/operator-overloads.md)
- [Wytyczne dotyczące projektowania — operatory równości](../../../standard/design-guidelines/equality-operators.md)
- [Dlaczego przeciążone operatory zawsze są statyczne w języku C#?](https://docs.microsoft.com/archive/blogs/ericlippert/why-are-overloaded-operators-always-static-in-c)
