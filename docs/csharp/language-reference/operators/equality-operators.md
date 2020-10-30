---
title: Operatory równości — odwołanie w C#
description: Dowiedz się więcej na temat operatorów porównania równości języka C# i równości typów języka C#.
ms.date: 10/30/2020
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 39461157c33fea0effb5c8808ded1c9981900e17
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063218"
---
# <a name="equality-operators-c-reference"></a><span data-ttu-id="161f3-103">Operatory równości (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="161f3-103">Equality operators (C# reference)</span></span>

<span data-ttu-id="161f3-104">Operatory [ `==` (równość)](#equality-operator-) i [ `!=` (nierówność)](#inequality-operator-) sprawdzają, czy ich operandy są równe, czy nie.</span><span class="sxs-lookup"><span data-stu-id="161f3-104">The [`==` (equality)](#equality-operator-) and [`!=` (inequality)](#inequality-operator-) operators check if their operands are equal or not.</span></span>

## <a name="equality-operator-"></a><span data-ttu-id="161f3-105">Operator równości = =</span><span class="sxs-lookup"><span data-stu-id="161f3-105">Equality operator ==</span></span>

<span data-ttu-id="161f3-106">Operator równości `==` zwraca `true` , jeśli jego operandy są równe, `false` w przeciwnym razie.</span><span class="sxs-lookup"><span data-stu-id="161f3-106">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

### <a name="value-types-equality"></a><span data-ttu-id="161f3-107">Równość typów wartości</span><span class="sxs-lookup"><span data-stu-id="161f3-107">Value types equality</span></span>

<span data-ttu-id="161f3-108">Argumenty operacji [wbudowanych typów wartości](../builtin-types/value-types.md#built-in-value-types) są równe, jeśli ich wartości są równe:</span><span class="sxs-lookup"><span data-stu-id="161f3-108">Operands of the [built-in value types](../builtin-types/value-types.md#built-in-value-types) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](snippets/shared/EqualityOperators.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="161f3-109">Dla `==` operatorów, [ `<` , `>` , `<=` i `>=` ](comparison-operators.md) , jeśli którykolwiek z operandów nie jest liczbą ( <xref:System.Double.NaN?displayProperty=nameWithType> lub <xref:System.Single.NaN?displayProperty=nameWithType> ), wynikiem operacji jest `false` .</span><span class="sxs-lookup"><span data-stu-id="161f3-109">For the `==`, [`<`, `>`, `<=`, and `>=`](comparison-operators.md) operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="161f3-110">Oznacza to, że `NaN` wartość nie jest większa niż, mniejsza niż ani równa żadnej innej `double` wartości (lub `float` ), w tym `NaN` .</span><span class="sxs-lookup"><span data-stu-id="161f3-110">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="161f3-111">Aby uzyskać więcej informacji i przykładów, zobacz <xref:System.Double.NaN?displayProperty=nameWithType> <xref:System.Single.NaN?displayProperty=nameWithType> artykuł lub dokumentacja.</span><span class="sxs-lookup"><span data-stu-id="161f3-111">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="161f3-112">Dwa operandy tego samego typu [wyliczeniowego](../builtin-types/enum.md) są równe, jeśli odpowiadające wartości bazowego typu całkowitego są równe.</span><span class="sxs-lookup"><span data-stu-id="161f3-112">Two operands of the same [enum](../builtin-types/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="161f3-113">Zdefiniowane przez użytkownika typy [struktur](../builtin-types/struct.md) nie obsługują `==` operatora domyślnie.</span><span class="sxs-lookup"><span data-stu-id="161f3-113">User-defined [struct](../builtin-types/struct.md) types don't support the `==` operator by default.</span></span> <span data-ttu-id="161f3-114">Aby zapewnić obsługę `==` operatora, struktura zdefiniowana przez użytkownika musi [przeciążać](operator-overloading.md) ją.</span><span class="sxs-lookup"><span data-stu-id="161f3-114">To support the `==` operator, a user-defined struct must [overload](operator-overloading.md) it.</span></span>

<span data-ttu-id="161f3-115">Począwszy od języka C# 7,3 `==` Operatory i `!=` są obsługiwane przez [krotki](../builtin-types/value-tuples.md)języka c#.</span><span class="sxs-lookup"><span data-stu-id="161f3-115">Beginning with C# 7.3, the `==` and `!=` operators are supported by C# [tuples](../builtin-types/value-tuples.md).</span></span> <span data-ttu-id="161f3-116">Aby uzyskać więcej informacji, zobacz sekcję [równość krotki](../builtin-types/value-tuples.md#tuple-equality) w artykule [typy krotek](../builtin-types/value-tuples.md) .</span><span class="sxs-lookup"><span data-stu-id="161f3-116">For more information, see the [Tuple equality](../builtin-types/value-tuples.md#tuple-equality) section of the [Tuple types](../builtin-types/value-tuples.md) article.</span></span>

### <a name="reference-types-equality"></a><span data-ttu-id="161f3-117">Równość typów referencyjnych</span><span class="sxs-lookup"><span data-stu-id="161f3-117">Reference types equality</span></span>

<span data-ttu-id="161f3-118">Domyślnie dwa operandy typu odwołania, które nie są rekordami, są równe, jeśli odwołują się do tego samego obiektu:</span><span class="sxs-lookup"><span data-stu-id="161f3-118">By default, two non-record reference-type operands are equal if they refer to the same object:</span></span>

[!code-csharp[reference type equality](snippets/shared/EqualityOperators.cs#ReferenceTypesEquality)]

<span data-ttu-id="161f3-119">Jak pokazano na przykładzie, zdefiniowane przez użytkownika typy odwołań domyślnie obsługują `==` operatora.</span><span class="sxs-lookup"><span data-stu-id="161f3-119">As the example shows, user-defined reference types support the `==` operator by default.</span></span> <span data-ttu-id="161f3-120">Jednak typ referencyjny może przeciążać `==` operator.</span><span class="sxs-lookup"><span data-stu-id="161f3-120">However, a reference type can overload the `==` operator.</span></span> <span data-ttu-id="161f3-121">Jeśli typ referencyjny przeciąża `==` operatora, użyj <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> metody, aby sprawdzić, czy dwa odwołania tego typu odwołują się do tego samego obiektu.</span><span class="sxs-lookup"><span data-stu-id="161f3-121">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

### <a name="record-types-equality"></a><span data-ttu-id="161f3-122">Równość typów rekordów</span><span class="sxs-lookup"><span data-stu-id="161f3-122">Record types equality</span></span>

<span data-ttu-id="161f3-123">W języku C# 9,0 i nowszych [typy rekordów](../../whats-new/csharp-9.md#record-types) obsługują `==` `!=` Operatory i, które domyślnie udostępniają semantykę równości wartości.</span><span class="sxs-lookup"><span data-stu-id="161f3-123">Available in C# 9.0 and later, [record types](../../whats-new/csharp-9.md#record-types) support the `==` and `!=` operators that by default provide value equality semantics.</span></span> <span data-ttu-id="161f3-124">Oznacza to, że dwa operandy rekordu są równe, gdy oba z nich są `null` lub odpowiadające wartości wszystkich pól i właściwości zaimplementowane domyślnie są równe.</span><span class="sxs-lookup"><span data-stu-id="161f3-124">That is, two record operands are equal when both of them are `null` or corresponding values of all fields and auto-implemented properties are equal.</span></span>

:::code language="csharp" source="snippets/shared/EqualityOperators.cs" id="RecordTypesEquality":::

<span data-ttu-id="161f3-125">Jak pokazano w powyższym przykładzie, w przypadku odwołań nienależących do rekordów, ich wartości odniesienia są porównywane, a nie wystąpienia przywoływane.</span><span class="sxs-lookup"><span data-stu-id="161f3-125">As the preceding example shows, in case of non-record reference-type members their reference values are compared, not the referenced instances.</span></span>

### <a name="string-equality"></a><span data-ttu-id="161f3-126">Równość ciągów</span><span class="sxs-lookup"><span data-stu-id="161f3-126">String equality</span></span>

<span data-ttu-id="161f3-127">Dwa operandy [ciągu](../builtin-types/reference-types.md#the-string-type) są równe, gdy oba z nich są `null` lub oba wystąpienia ciągu mają taką samą długość i mają identyczne znaki w każdej pozycji znaku:</span><span class="sxs-lookup"><span data-stu-id="161f3-127">Two [string](../builtin-types/reference-types.md#the-string-type) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](snippets/shared/EqualityOperators.cs#StringEquality)]

<span data-ttu-id="161f3-128">Jest to porównanie porządkowe z uwzględnieniem wielkości liter.</span><span class="sxs-lookup"><span data-stu-id="161f3-128">That is a case-sensitive ordinal comparison.</span></span> <span data-ttu-id="161f3-129">Aby uzyskać więcej informacji na temat porównywania ciągów, zobacz [Jak porównać ciągi w języku C#](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="161f3-129">For more information about string comparison, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

### <a name="delegate-equality"></a><span data-ttu-id="161f3-130">Równość delegowania</span><span class="sxs-lookup"><span data-stu-id="161f3-130">Delegate equality</span></span>

<span data-ttu-id="161f3-131">Dwa operandy [delegatów](../../programming-guide/delegates/index.md) tego samego typu środowiska uruchomieniowego są równe, gdy oba z nich są `null` lub ich listy wywołań mają taką samą długość i mają równe wpisy w każdej pozycji:</span><span class="sxs-lookup"><span data-stu-id="161f3-131">Two [delegate](../../programming-guide/delegates/index.md) operands of the same runtime type are equal when both of them are `null` or their invocation lists are of the same length and have equal entries in each position:</span></span>

[!code-csharp-interactive[delegate equality](snippets/shared/EqualityOperators.cs#DelegateEquality)]

<span data-ttu-id="161f3-132">Aby uzyskać więcej informacji, zobacz sekcję [delegowanie operatorów równości](~/_csharplang/spec/expressions.md#delegate-equality-operators) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="161f3-132">For more information, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="161f3-133">Delegaty wytwarzane z oceny semantycznie identycznych [wyrażeń lambda](lambda-expressions.md) nie są równe, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="161f3-133">Delegates that are produced from evaluation of semantically identical [lambda expressions](lambda-expressions.md) are not equal, as the following example shows:</span></span>

[!code-csharp-interactive[from identical lambdas](snippets/shared/EqualityOperators.cs#IdenticalLambdas)]

## <a name="inequality-operator-"></a><span data-ttu-id="161f3-134">Operator nierówności! =</span><span class="sxs-lookup"><span data-stu-id="161f3-134">Inequality operator !=</span></span>

<span data-ttu-id="161f3-135">Operator nierówności `!=` zwraca `true` , jeśli jego operandy nie są równe `false` . w przeciwnym razie.</span><span class="sxs-lookup"><span data-stu-id="161f3-135">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="161f3-136">W przypadku operandów [typów wbudowanych](../builtin-types/built-in-types.md)wyrażenie `x != y` daje ten sam wynik co wyrażenie `!(x == y)` .</span><span class="sxs-lookup"><span data-stu-id="161f3-136">For the operands of the [built-in types](../builtin-types/built-in-types.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="161f3-137">Aby uzyskać więcej informacji na temat równości typów, zobacz sekcję [operator równości](#equality-operator-) .</span><span class="sxs-lookup"><span data-stu-id="161f3-137">For more information about type equality, see the [Equality operator](#equality-operator-) section.</span></span>

<span data-ttu-id="161f3-138">Poniższy przykład ilustruje użycie `!=` operatora:</span><span class="sxs-lookup"><span data-stu-id="161f3-138">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](snippets/shared/EqualityOperators.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="161f3-139">Przeciążanie operatora</span><span class="sxs-lookup"><span data-stu-id="161f3-139">Operator overloadability</span></span>

<span data-ttu-id="161f3-140">Typ zdefiniowany przez użytkownika może [przeciążać](operator-overloading.md) `==` `!=` Operatory i.</span><span class="sxs-lookup"><span data-stu-id="161f3-140">A user-defined type can [overload](operator-overloading.md) the `==` and `!=` operators.</span></span> <span data-ttu-id="161f3-141">Jeśli typ przeciąża jeden z dwóch operatorów, musi on również przeciążać pozostałe.</span><span class="sxs-lookup"><span data-stu-id="161f3-141">If a type overloads one of the two operators, it must also overload the other one.</span></span>

<span data-ttu-id="161f3-142">Typ rekordu nie może jawnie przeciążać `==` `!=` operatorów i.</span><span class="sxs-lookup"><span data-stu-id="161f3-142">A record type cannot explicitly overload the `==` and `!=` operators.</span></span> <span data-ttu-id="161f3-143">Jeśli musisz zmienić zachowanie `==` `!=` operatorów i dla typu rekordu `T` , zaimplementuj <xref:System.IEquatable%601.Equals%2A?displayProperty=nameWithType> metodę następującym podpisem:</span><span class="sxs-lookup"><span data-stu-id="161f3-143">If you need to change the behavior of the `==` and `!=` operators for record type `T`, implement the <xref:System.IEquatable%601.Equals%2A?displayProperty=nameWithType> method with the following signature:</span></span>

```csharp
public virtual bool Equals(T? other);
```

## <a name="c-language-specification"></a><span data-ttu-id="161f3-144">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="161f3-144">C# language specification</span></span>

<span data-ttu-id="161f3-145">Aby uzyskać więcej informacji, zobacz sekcję [Operatory relacyjne i testowe typu](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="161f3-145">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="161f3-146">Aby uzyskać więcej informacji na temat równości typów rekordów, zobacz sekcję z [członkami równości](~/_csharplang/proposals/csharp-9.0/records.md#equality-members) w temacie [Records propozycja funkcji](~/_csharplang/proposals/csharp-9.0/records.md).</span><span class="sxs-lookup"><span data-stu-id="161f3-146">For more information about equality of record types, see the [Equality members](~/_csharplang/proposals/csharp-9.0/records.md#equality-members) section of the [records feature proposal note](~/_csharplang/proposals/csharp-9.0/records.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="161f3-147">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="161f3-147">See also</span></span>

- [<span data-ttu-id="161f3-148">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="161f3-148">C# reference</span></span>](../index.md)
- [<span data-ttu-id="161f3-149">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="161f3-149">C# operators and expressions</span></span>](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="161f3-150">Porównywanie równości</span><span class="sxs-lookup"><span data-stu-id="161f3-150">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [<span data-ttu-id="161f3-151">Operatory porównania</span><span class="sxs-lookup"><span data-stu-id="161f3-151">Comparison operators</span></span>](comparison-operators.md)
