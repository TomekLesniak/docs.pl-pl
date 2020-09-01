---
description: + Operatory and + = — odwołanie w C#
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
ms.openlocfilehash: 00ba020939694d901afdbf5f5f93b584363d2cc7
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141858"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="ceeeb-103">Operatory + i + = (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="ceeeb-103">+ and += operators (C# reference)</span></span>

<span data-ttu-id="ceeeb-104">`+`Operatory i `+=` są obsługiwane przez wbudowane typy liczbowe [całkowite](../builtin-types/integral-numeric-types.md) i [zmiennoprzecinkowe](../builtin-types/floating-point-numeric-types.md) , typ [ciągu](../builtin-types/reference-types.md#the-string-type) i typy [delegatów](../builtin-types/reference-types.md#the-delegate-type) .</span><span class="sxs-lookup"><span data-stu-id="ceeeb-104">The `+` and `+=` operators are supported by the built-in [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types, the [string](../builtin-types/reference-types.md#the-string-type) type, and [delegate](../builtin-types/reference-types.md#the-delegate-type) types.</span></span>

<span data-ttu-id="ceeeb-105">Aby uzyskać informacje o `+` operatorze arytmetycznym, zobacz [operatory jednoargumentowe Plus i minus](arithmetic-operators.md#unary-plus-and-minus-operators) oraz [operator dodawania +](arithmetic-operators.md#addition-operator-) sekcje w artykule [Operatory arytmetyczne](arithmetic-operators.md) .</span><span class="sxs-lookup"><span data-stu-id="ceeeb-105">For information about the arithmetic `+` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Addition operator +](arithmetic-operators.md#addition-operator-) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="ceeeb-106">Łączenie ciągów</span><span class="sxs-lookup"><span data-stu-id="ceeeb-106">String concatenation</span></span>

<span data-ttu-id="ceeeb-107">Gdy jeden lub oba operandy są typu [String](../builtin-types/reference-types.md#the-string-type), `+` operator łączy reprezentacje ciągów argumentów operacji (ciąg reprezentacja `null` jest ciągiem pustym):</span><span class="sxs-lookup"><span data-stu-id="ceeeb-107">When one or both operands are of type [string](../builtin-types/reference-types.md#the-string-type), the `+` operator concatenates the string representations of its operands (the string representation of `null` is an empty string):</span></span>

[!code-csharp-interactive[string concatenation](snippets/shared/AdditionOperator.cs#AddStrings)]

<span data-ttu-id="ceeeb-108">Począwszy od języka C# 6, [Interpolacja ciągów](../tokens/interpolated.md) zapewnia wygodniejszy sposób formatowania ciągów:</span><span class="sxs-lookup"><span data-stu-id="ceeeb-108">Beginning with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](snippets/shared/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="ceeeb-109">Połączenie delegata</span><span class="sxs-lookup"><span data-stu-id="ceeeb-109">Delegate combination</span></span>

<span data-ttu-id="ceeeb-110">W przypadku operandów tego samego typu [delegata](../builtin-types/reference-types.md#the-delegate-type) `+` operator zwraca nowe wystąpienie delegata, które po wywołaniu wywołuje argument operacji po lewej stronie, a następnie wywołuje operand z prawej strony.</span><span class="sxs-lookup"><span data-stu-id="ceeeb-110">For operands of the same [delegate](../builtin-types/reference-types.md#the-delegate-type) type, the `+` operator returns a new delegate instance that, when invoked, invokes the left-hand operand and then invokes the right-hand operand.</span></span> <span data-ttu-id="ceeeb-111">Jeśli którykolwiek z operandów jest `null` , `+` operator zwraca wartość innego operandu (co również może być `null` ).</span><span class="sxs-lookup"><span data-stu-id="ceeeb-111">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="ceeeb-112">Poniższy przykład pokazuje, jak można łączyć delegatów z `+` operatorem:</span><span class="sxs-lookup"><span data-stu-id="ceeeb-112">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](snippets/shared/AdditionOperator.cs#AddDelegates)]

<span data-ttu-id="ceeeb-113">Aby przeprowadzić usuwanie delegata, użyj [ `-` operatora](subtraction-operator.md#delegate-removal).</span><span class="sxs-lookup"><span data-stu-id="ceeeb-113">To perform delegate removal, use the [`-` operator](subtraction-operator.md#delegate-removal).</span></span>

<span data-ttu-id="ceeeb-114">Aby uzyskać więcej informacji na temat typów delegatów, zobacz [delegats](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="ceeeb-114">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="addition-assignment-operator-"></a><span data-ttu-id="ceeeb-115">Operator przypisania dodawania + =</span><span class="sxs-lookup"><span data-stu-id="ceeeb-115">Addition assignment operator +=</span></span>

<span data-ttu-id="ceeeb-116">Wyrażenie używające `+=` operatora, takie jak</span><span class="sxs-lookup"><span data-stu-id="ceeeb-116">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="ceeeb-117">jest równoważny</span><span class="sxs-lookup"><span data-stu-id="ceeeb-117">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="ceeeb-118">z tą różnicą, że `x` jest obliczana tylko raz.</span><span class="sxs-lookup"><span data-stu-id="ceeeb-118">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="ceeeb-119">Poniższy przykład ilustruje użycie `+=` operatora:</span><span class="sxs-lookup"><span data-stu-id="ceeeb-119">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](snippets/shared/AdditionOperator.cs#AddAndAssign)]

<span data-ttu-id="ceeeb-120">Możesz również użyć `+=` operatora, aby określić metodę procedury obsługi zdarzeń podczas subskrybowania [zdarzenia](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="ceeeb-120">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="ceeeb-121">Aby uzyskać więcej informacji, zobacz [How to: subskrybowanie i anulowanie subskrypcji zdarzeń](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="ceeeb-121">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="ceeeb-122">Przeciążanie operatora</span><span class="sxs-lookup"><span data-stu-id="ceeeb-122">Operator overloadability</span></span>

<span data-ttu-id="ceeeb-123">Typ zdefiniowany przez użytkownika może [przeciążać](operator-overloading.md) `+` operatora.</span><span class="sxs-lookup"><span data-stu-id="ceeeb-123">A user-defined type can [overload](operator-overloading.md) the `+` operator.</span></span> <span data-ttu-id="ceeeb-124">Gdy operator binarny `+` jest przeciążony, `+=` operator jest również niejawnie przeciążony.</span><span class="sxs-lookup"><span data-stu-id="ceeeb-124">When a binary `+` operator is overloaded, the `+=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="ceeeb-125">Typ zdefiniowany przez użytkownika nie może jawnie przeciążać `+=` operatora.</span><span class="sxs-lookup"><span data-stu-id="ceeeb-125">A user-defined type cannot explicitly overload the `+=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ceeeb-126">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="ceeeb-126">C# language specification</span></span>

<span data-ttu-id="ceeeb-127">Aby uzyskać więcej informacji, zobacz sekcje [jednoargumentowe Plus](~/_csharplang/spec/expressions.md#unary-plus-operator) i [operator dodawania](~/_csharplang/spec/expressions.md#addition-operator) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="ceeeb-127">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ceeeb-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ceeeb-128">See also</span></span>

- [<span data-ttu-id="ceeeb-129">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="ceeeb-129">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ceeeb-130">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="ceeeb-130">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="ceeeb-131">Jak połączyć wiele ciągów</span><span class="sxs-lookup"><span data-stu-id="ceeeb-131">How to concatenate multiple strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="ceeeb-132">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="ceeeb-132">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="ceeeb-133">Operatory arytmetyczne</span><span class="sxs-lookup"><span data-stu-id="ceeeb-133">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="ceeeb-134">Operatory-and-=</span><span class="sxs-lookup"><span data-stu-id="ceeeb-134">- and -= operators</span></span>](subtraction-operator.md)
