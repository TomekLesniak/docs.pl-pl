---
title: Typy wartości null — odwołanie w C#
description: Dowiedz się więcej o typach wartości null języka C# i sposobach ich użycia
ms.date: 11/04/2019
helpviewer_keywords:
- nullable value types [C#]
ms.openlocfilehash: 3ab2dff6b7399b0458a69d4498b2ebda24f6c5cc
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471838"
---
# <a name="nullable-value-types-c-reference"></a><span data-ttu-id="a76d7-103">Typy wartości null (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="a76d7-103">Nullable value types (C# reference)</span></span>

<span data-ttu-id="a76d7-104">*Typ wartości null* `T?` reprezentuje wszystkie wartości jego bazowego [typu wartości](value-types.md) `T` oraz dodatkową wartość [null](../keywords/null.md) .</span><span class="sxs-lookup"><span data-stu-id="a76d7-104">A *nullable value type* `T?` represents all values of its underlying [value type](value-types.md) `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="a76d7-105">Na przykład można przypisać jedną z następujących trzech wartości do `bool?` zmiennej: `true` , `false` , lub `null` .</span><span class="sxs-lookup"><span data-stu-id="a76d7-105">For example, you can assign any of the following three values to a `bool?` variable: `true`, `false`, or `null`.</span></span> <span data-ttu-id="a76d7-106">Podstawowy typ wartości `T` nie może być samym typem wartości null.</span><span class="sxs-lookup"><span data-stu-id="a76d7-106">An underlying value type `T` cannot be a nullable value type itself.</span></span>

> [!NOTE]
> <span data-ttu-id="a76d7-107">W języku C# 8,0 wprowadzono funkcję typów referencyjnych dopuszczających wartość null.</span><span class="sxs-lookup"><span data-stu-id="a76d7-107">C# 8.0 introduces the nullable reference types feature.</span></span> <span data-ttu-id="a76d7-108">Aby uzyskać więcej informacji, zobacz [typy referencyjne dopuszczające wartość null](nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="a76d7-108">For more information, see [Nullable reference types](nullable-reference-types.md).</span></span> <span data-ttu-id="a76d7-109">Typy wartości null są dostępne począwszy od języka C# 2.</span><span class="sxs-lookup"><span data-stu-id="a76d7-109">The nullable value types are available beginning with C# 2.</span></span>

<span data-ttu-id="a76d7-110">Każdy typ wartości null jest wystąpieniem <xref:System.Nullable%601?displayProperty=nameWithType> struktury ogólnej.</span><span class="sxs-lookup"><span data-stu-id="a76d7-110">Any nullable value type is an instance of the generic <xref:System.Nullable%601?displayProperty=nameWithType> structure.</span></span> <span data-ttu-id="a76d7-111">Można odwołać się do typu wartości null z typem bazowym `T` w dowolnej z następujących metod zamiennych: `Nullable<T>` lub `T?` .</span><span class="sxs-lookup"><span data-stu-id="a76d7-111">You can refer to a nullable value type with an underlying type `T` in any of the following interchangeable forms: `Nullable<T>` or `T?`.</span></span>

<span data-ttu-id="a76d7-112">Typ wartości null jest zazwyczaj używany, gdy trzeba reprezentować niezdefiniowaną wartość bazowego typu wartości.</span><span class="sxs-lookup"><span data-stu-id="a76d7-112">You typically use a nullable value type when you need to represent the undefined value of an underlying value type.</span></span> <span data-ttu-id="a76d7-113">Na przykład wartość logiczna lub `bool` zmienna może mieć wartość `true` lub `false` .</span><span class="sxs-lookup"><span data-stu-id="a76d7-113">For example, a Boolean, or `bool`, variable can only be either `true` or `false`.</span></span> <span data-ttu-id="a76d7-114">Jednak w niektórych aplikacjach wartość zmiennej może być niezdefiniowana lub brakująca.</span><span class="sxs-lookup"><span data-stu-id="a76d7-114">However, in some applications a variable value can be undefined or missing.</span></span> <span data-ttu-id="a76d7-115">Na przykład pole bazy danych może zawierać `true` lub lub `false` nie może zawierać żadnej wartości, czyli `NULL` .</span><span class="sxs-lookup"><span data-stu-id="a76d7-115">For example, a database field may contain `true` or `false`, or it may contain no value at all, that is, `NULL`.</span></span> <span data-ttu-id="a76d7-116">Możesz użyć `bool?` typu w tym scenariuszu.</span><span class="sxs-lookup"><span data-stu-id="a76d7-116">You can use the `bool?` type in that scenario.</span></span>

## <a name="declaration-and-assignment"></a><span data-ttu-id="a76d7-117">Deklaracja i przypisanie</span><span class="sxs-lookup"><span data-stu-id="a76d7-117">Declaration and assignment</span></span>

<span data-ttu-id="a76d7-118">Ponieważ typ wartości jest niejawnie konwertowany do odpowiadającego typu wartości null, można przypisać wartość do zmiennej typu wartości null, tak jak w przypadku jego bazowego typu wartości.</span><span class="sxs-lookup"><span data-stu-id="a76d7-118">As a value type is implicitly convertible to the corresponding nullable value type, you can assign a value to a variable of a nullable value type as you would do that for its underlying value type.</span></span> <span data-ttu-id="a76d7-119">Możesz również przypisać `null` wartość.</span><span class="sxs-lookup"><span data-stu-id="a76d7-119">You can also assign the `null` value.</span></span> <span data-ttu-id="a76d7-120">Przykład:</span><span class="sxs-lookup"><span data-stu-id="a76d7-120">For example:</span></span>

[!code-csharp[declare and assign](snippets/shared/NullableValueTypes.cs#Declaration)]

<span data-ttu-id="a76d7-121">Wartość domyślna typu wartości null reprezentuje `null` , czyli to wystąpienie, którego <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> Właściwość zwraca `false` .</span><span class="sxs-lookup"><span data-stu-id="a76d7-121">The default value of a nullable value type represents `null`, that is, it's an instance whose <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> property returns `false`.</span></span>

## <a name="examination-of-an-instance-of-a-nullable-value-type"></a><span data-ttu-id="a76d7-122">Badanie wystąpienia typu wartości null</span><span class="sxs-lookup"><span data-stu-id="a76d7-122">Examination of an instance of a nullable value type</span></span>

<span data-ttu-id="a76d7-123">Począwszy od języka C# 7,0, można użyć [ `is` operatora ze wzorcem typu](../operators/type-testing-and-cast.md#type-testing-with-pattern-matching) do obu badań wystąpienie typu wartości null dla `null` i pobrać wartość typu podstawowego:</span><span class="sxs-lookup"><span data-stu-id="a76d7-123">Beginning with C# 7.0, you can use the [`is` operator with a type pattern](../operators/type-testing-and-cast.md#type-testing-with-pattern-matching) to both examine an instance of a nullable value type for `null` and retrieve a value of an underlying type:</span></span>

[!code-csharp-interactive[use pattern matching](snippets/shared/NullableValueTypes.cs#PatternMatching)]

<span data-ttu-id="a76d7-124">Aby sprawdzać i pobierać wartość zmiennej typu wartości null, zawsze można użyć następujących właściwości tylko do odczytu:</span><span class="sxs-lookup"><span data-stu-id="a76d7-124">You always can use the following read-only properties to examine and get a value of a nullable value type variable:</span></span>

- <span data-ttu-id="a76d7-125"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> wskazuje, czy wystąpienie typu wartości null ma wartość jego typu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="a76d7-125"><xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> indicates whether an instance of a nullable value type has a value of its underlying type.</span></span>

- <span data-ttu-id="a76d7-126"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> Pobiera wartość typu podstawowego, jeśli <xref:System.Nullable%601.HasValue%2A> jest `true` .</span><span class="sxs-lookup"><span data-stu-id="a76d7-126"><xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> gets the value of an underlying type if <xref:System.Nullable%601.HasValue%2A> is `true`.</span></span> <span data-ttu-id="a76d7-127">Jeśli <xref:System.Nullable%601.HasValue%2A> ma wartość `false` , <xref:System.Nullable%601.Value%2A> Właściwość zgłasza <xref:System.InvalidOperationException> .</span><span class="sxs-lookup"><span data-stu-id="a76d7-127">If <xref:System.Nullable%601.HasValue%2A> is `false`, the <xref:System.Nullable%601.Value%2A> property throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="a76d7-128">Poniższy przykład używa właściwości, `HasValue` Aby sprawdzić, czy zmienna zawiera wartość przed wyświetleniem:</span><span class="sxs-lookup"><span data-stu-id="a76d7-128">The following example uses the `HasValue` property to test whether the variable contains a value before displaying it:</span></span>

[!code-csharp-interactive[use HasValue](snippets/shared/NullableValueTypes.cs#HasValue)]

<span data-ttu-id="a76d7-129">Możesz również porównać zmienną typu wartości null z `null` zamiast używać `HasValue` właściwości, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="a76d7-129">You can also compare a variable of a nullable value type with `null` instead of using the `HasValue` property, as the following example shows:</span></span>

[!code-csharp-interactive[use comparison with null](snippets/shared/NullableValueTypes.cs#CompareWithNull)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a><span data-ttu-id="a76d7-130">Konwersja z typu wartości null na typ podstawowy</span><span class="sxs-lookup"><span data-stu-id="a76d7-130">Conversion from a nullable value type to an underlying type</span></span>

<span data-ttu-id="a76d7-131">Jeśli chcesz przypisać wartość typu wartości null do zmiennej typu wartości, która nie dopuszcza wartości null, może być konieczne określenie wartości, która ma zostać przypisana zamiast `null` .</span><span class="sxs-lookup"><span data-stu-id="a76d7-131">If you want to assign a value of a nullable value type to a non-nullable value type variable, you might need to specify the value to be assigned in place of `null`.</span></span> <span data-ttu-id="a76d7-132">Użyj [ `??` operatora łączenia wartości null](../operators/null-coalescing-operator.md) , aby to zrobić (można również użyć <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> metody do tego samego celu):</span><span class="sxs-lookup"><span data-stu-id="a76d7-132">Use the [null-coalescing operator `??`](../operators/null-coalescing-operator.md) to do that (you can also use the <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> method for the same purpose):</span></span>

[!code-csharp-interactive[?? operator](snippets/shared/NullableValueTypes.cs#NullCoalescing)]

<span data-ttu-id="a76d7-133">Jeśli chcesz użyć [domyślnej](default-values.md) wartości bazowego typu wartości zamiast `null` , użyj <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="a76d7-133">If you want to use the [default](default-values.md) value of the underlying value type in place of `null`, use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="a76d7-134">Można również jawnie rzutować typ wartości null na typ niedopuszczający wartości null, co ilustruje poniższy przykład:</span><span class="sxs-lookup"><span data-stu-id="a76d7-134">You can also explicitly cast a nullable value type to a non-nullable type, as the following example shows:</span></span>

[!code-csharp[explicit cast](snippets/shared/NullableValueTypes.cs#Cast)]

<span data-ttu-id="a76d7-135">W czasie wykonywania, jeśli wartość typu wartości null to `null` , jawne rzutowanie zgłosi <xref:System.InvalidOperationException> .</span><span class="sxs-lookup"><span data-stu-id="a76d7-135">At run time, if the value of a nullable value type is `null`, the explicit cast throws an <xref:System.InvalidOperationException>.</span></span>

<span data-ttu-id="a76d7-136">Typ wartości niedopuszczający wartości null `T` jest niejawnie konwertowany na odpowiedni typ wartości null `T?` .</span><span class="sxs-lookup"><span data-stu-id="a76d7-136">A non-nullable value type `T` is implicitly convertible to the corresponding nullable value type `T?`.</span></span>

## <a name="lifted-operators"></a><span data-ttu-id="a76d7-137">Podniesione operatory</span><span class="sxs-lookup"><span data-stu-id="a76d7-137">Lifted operators</span></span>

<span data-ttu-id="a76d7-138">Wstępnie zdefiniowane [Operatory](../operators/index.md) jednoargumentowe i binarne lub wszelkie przeciążone operatory obsługiwane przez typ wartości `T` są również obsługiwane przez odpowiedni typ wartości null `T?` .</span><span class="sxs-lookup"><span data-stu-id="a76d7-138">The predefined unary and binary [operators](../operators/index.md) or any overloaded operators that are supported by a value type `T` are also supported by the corresponding nullable value type `T?`.</span></span> <span data-ttu-id="a76d7-139">Te operatory, znane także jako *zniesione operatory*, tworzą, `null` Jeśli jeden lub oba operandy są `null` ; w przeciwnym razie operator używa zawartych wartości argumentów operacji, aby obliczyć wynik.</span><span class="sxs-lookup"><span data-stu-id="a76d7-139">These operators, also known as *lifted operators*, produce `null` if one or both operands are `null`; otherwise, the operator uses the contained values of its operands to calculate the result.</span></span> <span data-ttu-id="a76d7-140">Przykład:</span><span class="sxs-lookup"><span data-stu-id="a76d7-140">For example:</span></span>

[!code-csharp[lifted operators](snippets/shared/NullableValueTypes.cs#LiftedOperator)]

> [!NOTE]
> <span data-ttu-id="a76d7-141">Dla `bool?` typu, wstępnie zdefiniowane `&` Operatory i `|` nie przestrzegają zasad opisanych w tej sekcji: wynik oceny operatora może być inny niż null, nawet jeśli jeden z operandów jest `null` .</span><span class="sxs-lookup"><span data-stu-id="a76d7-141">For the `bool?` type, the predefined `&` and `|` operators don't follow the rules described in this section: the result of an operator evaluation can be non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="a76d7-142">Aby uzyskać więcej informacji, zobacz sekcję [Operatory logiczne wartości null](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) w artykule [Operatory logiczne Boolean](../operators/boolean-logical-operators.md) .</span><span class="sxs-lookup"><span data-stu-id="a76d7-142">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

<span data-ttu-id="a76d7-143">W przypadku [operatorów porównania](../operators/comparison-operators.md) `<` , `>` , `<=` i `>=` , jeśli jeden lub oba operandy są `null` , wynikiem jest `false` ; w przeciwnym razie zawarte wartości argumentów operacji są porównywane.</span><span class="sxs-lookup"><span data-stu-id="a76d7-143">For the [comparison operators](../operators/comparison-operators.md) `<`, `>`, `<=`, and `>=`, if one or both operands are `null`, the result is `false`; otherwise, the contained values of operands are compared.</span></span> <span data-ttu-id="a76d7-144">Nie należy zakładać, że ponieważ określone porównanie (na przykład `<=` ) zwraca `false` , odwrotne porównanie ( `>` ) zwraca wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="a76d7-144">Do not assume that because a particular comparison (for example, `<=`) returns `false`, the opposite comparison (`>`) returns `true`.</span></span> <span data-ttu-id="a76d7-145">Poniższy przykład pokazuje, że 10 jest</span><span class="sxs-lookup"><span data-stu-id="a76d7-145">The following example shows that 10 is</span></span>

- <span data-ttu-id="a76d7-146">nie większe niż lub równe `null`</span><span class="sxs-lookup"><span data-stu-id="a76d7-146">neither greater than or equal to `null`</span></span>
- <span data-ttu-id="a76d7-147">nie mniejsze niż `null`</span><span class="sxs-lookup"><span data-stu-id="a76d7-147">nor less than `null`</span></span>

[!code-csharp-interactive[relational and equality operators](snippets/shared/NullableValueTypes.cs#ComparisonOperators)]

<span data-ttu-id="a76d7-148">W przypadku [operatora równości](../operators/equality-operators.md#equality-operator-) `==` , jeśli oba operandy są `null` , wynikiem jest `true` , jeśli tylko jeden z operandów ma wartość, `null` wynik to `false` ; w przeciwnym razie zawarte wartości argumentów operacji są porównywane.</span><span class="sxs-lookup"><span data-stu-id="a76d7-148">For the [equality operator](../operators/equality-operators.md#equality-operator-) `==`, if both operands are `null`, the result is `true`, if only one of the operands is `null`, the result is `false`; otherwise, the contained values of operands are compared.</span></span>

<span data-ttu-id="a76d7-149">W przypadku [operatora nierówności](../operators/equality-operators.md#inequality-operator-) `!=` , jeśli oba operandy są `null` , wynikiem jest `false` , jeśli tylko jeden z operandów ma wartość, `null` wynik to `true` ; w przeciwnym razie zawarte wartości argumentów operacji są porównywane.</span><span class="sxs-lookup"><span data-stu-id="a76d7-149">For the [inequality operator](../operators/equality-operators.md#inequality-operator-) `!=`, if both operands are `null`, the result is `false`, if only one of the operands is `null`, the result is `true`; otherwise, the contained values of operands are compared.</span></span>

<span data-ttu-id="a76d7-150">Jeśli istnieje [konwersja zdefiniowana przez użytkownika](../operators/user-defined-conversion-operators.md) między dwoma typami wartości, można także użyć tej samej konwersji między odpowiednimi typami wartości null.</span><span class="sxs-lookup"><span data-stu-id="a76d7-150">If there exists a [user-defined conversion](../operators/user-defined-conversion-operators.md) between two value types, the same conversion can also be used between the corresponding nullable value types.</span></span>

## <a name="boxing-and-unboxing"></a><span data-ttu-id="a76d7-151">Pakowanie i rozpakowywanie</span><span class="sxs-lookup"><span data-stu-id="a76d7-151">Boxing and unboxing</span></span>

<span data-ttu-id="a76d7-152">Wystąpienie typu wartości null `T?` jest [opakowane](../../programming-guide/types/boxing-and-unboxing.md) w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="a76d7-152">An instance of a nullable value type `T?` is [boxed](../../programming-guide/types/boxing-and-unboxing.md) as follows:</span></span>

- <span data-ttu-id="a76d7-153">Jeśli <xref:System.Nullable%601.HasValue%2A> zwraca `false` , zostanie utworzone odwołanie o wartości null.</span><span class="sxs-lookup"><span data-stu-id="a76d7-153">If <xref:System.Nullable%601.HasValue%2A> returns `false`, the null reference is produced.</span></span>
- <span data-ttu-id="a76d7-154">Jeśli <xref:System.Nullable%601.HasValue%2A> zwraca `true` , odpowiadająca wartość bazowego typu wartości `T` jest opakowana, a nie wystąpieniem <xref:System.Nullable%601> .</span><span class="sxs-lookup"><span data-stu-id="a76d7-154">If <xref:System.Nullable%601.HasValue%2A> returns `true`, the corresponding value of the underlying value type `T` is boxed, not the instance of <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="a76d7-155">Można Unbox wartość opakowaną typu wartości `T` do odpowiadającego typu wartości null `T?` , co ilustruje poniższy przykład:</span><span class="sxs-lookup"><span data-stu-id="a76d7-155">You can unbox a boxed value of a value type `T` to the corresponding nullable value type `T?`, as the following example shows:</span></span>

[!code-csharp-interactive[boxing and unboxing](snippets/shared/NullableValueTypes.cs#Boxing)]

## <a name="how-to-identify-a-nullable-value-type"></a><span data-ttu-id="a76d7-156">Jak zidentyfikować typ wartości null</span><span class="sxs-lookup"><span data-stu-id="a76d7-156">How to identify a nullable value type</span></span>

<span data-ttu-id="a76d7-157">Poniższy przykład pokazuje, jak ustalić, czy <xref:System.Type?displayProperty=nameWithType> wystąpienie reprezentuje skonstruowany typ wartości null, czyli <xref:System.Nullable%601?displayProperty=nameWithType> Typ z określonym parametrem typu `T` :</span><span class="sxs-lookup"><span data-stu-id="a76d7-157">The following example shows how to determine whether a <xref:System.Type?displayProperty=nameWithType> instance represents a constructed nullable value type, that is, the <xref:System.Nullable%601?displayProperty=nameWithType> type with a specified type parameter `T`:</span></span>

[!code-csharp-interactive[whether Type is nullable](snippets/shared/NullableValueTypes.cs#IsTypeNullable)]

<span data-ttu-id="a76d7-158">Jak pokazano w przykładzie, należy użyć operatora [typeof](../operators/type-testing-and-cast.md#typeof-operator) do utworzenia <xref:System.Type?displayProperty=nameWithType> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="a76d7-158">As the example shows, you use the [typeof](../operators/type-testing-and-cast.md#typeof-operator) operator to create a <xref:System.Type?displayProperty=nameWithType> instance.</span></span>

<span data-ttu-id="a76d7-159">Aby określić, czy wystąpienie ma typ wartości null, nie należy używać <xref:System.Object.GetType%2A?displayProperty=nameWithType> metody, aby uzyskać <xref:System.Type> wystąpienie do przetestowania przy użyciu poprzedniego kodu.</span><span class="sxs-lookup"><span data-stu-id="a76d7-159">If you want to determine whether an instance is of a nullable value type, don't use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method to get a <xref:System.Type> instance to be tested with the preceding code.</span></span> <span data-ttu-id="a76d7-160">Gdy wywoływana jest <xref:System.Object.GetType%2A?displayProperty=nameWithType> Metoda w wystąpieniu typu wartości null, wystąpienie jest [opakowane](#boxing-and-unboxing) na <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="a76d7-160">When you call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on an instance of a nullable value type, the instance is [boxed](#boxing-and-unboxing) to <xref:System.Object>.</span></span> <span data-ttu-id="a76d7-161">Jako opakowanie niezerowego typu wartości null jest równoważne z opakowaniem wartości typu podstawowego, <xref:System.Object.GetType%2A> zwraca <xref:System.Type> wystąpienie reprezentujące typ podstawowy typu wartości null:</span><span class="sxs-lookup"><span data-stu-id="a76d7-161">As boxing of a non-null instance of a nullable value type is equivalent to boxing of a value of the underlying type, <xref:System.Object.GetType%2A> returns a <xref:System.Type> instance that represents the underlying type of a nullable value type:</span></span>

[!code-csharp-interactive[GetType example](snippets/shared/NullableValueTypes.cs#GetType)]

<span data-ttu-id="a76d7-162">Ponadto nie należy używać operatora [is](../operators/type-testing-and-cast.md#is-operator) , aby określić, czy wystąpienie ma typ wartości null.</span><span class="sxs-lookup"><span data-stu-id="a76d7-162">Also, don't use the [is](../operators/type-testing-and-cast.md#is-operator) operator to determine whether an instance is of a nullable value type.</span></span> <span data-ttu-id="a76d7-163">Jak pokazano na poniższym przykładzie, nie można rozróżnić typów wystąpienia typu wartości null i jego wystąpienia podstawowego z `is` operatorem:</span><span class="sxs-lookup"><span data-stu-id="a76d7-163">As the following example shows, you cannot distinguish types of a nullable value type instance and its underlying type instance with the `is` operator:</span></span>

[!code-csharp-interactive[is operator example](snippets/shared/NullableValueTypes.cs#IsOperator)]

<span data-ttu-id="a76d7-164">Możesz użyć kodu przedstawionego w poniższym przykładzie, aby określić, czy wystąpienie ma typ wartości null:</span><span class="sxs-lookup"><span data-stu-id="a76d7-164">You can use the code presented in the following example to determine whether an instance is of a nullable value type:</span></span>

[!code-csharp-interactive[whether an instance is of a nullable type](snippets/shared/NullableValueTypes.cs#IsInstanceNullable)]

> [!NOTE]
> <span data-ttu-id="a76d7-165">Metody opisane w tej sekcji nie mają zastosowania w przypadku [typów referencyjnych dopuszczających wartość null](nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="a76d7-165">The methods described in this section are not applicable in the case of [nullable reference types](nullable-reference-types.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a76d7-166">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="a76d7-166">C# language specification</span></span>

<span data-ttu-id="a76d7-167">Aby uzyskać więcej informacji, zobacz następujące sekcje [specyfikacji języka C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="a76d7-167">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="a76d7-168">Typy dopuszczające wartości null</span><span class="sxs-lookup"><span data-stu-id="a76d7-168">Nullable types</span></span>](~/_csharplang/spec/types.md#nullable-types)
- [<span data-ttu-id="a76d7-169">Podniesione operatory</span><span class="sxs-lookup"><span data-stu-id="a76d7-169">Lifted operators</span></span>](~/_csharplang/spec/expressions.md#lifted-operators)
- [<span data-ttu-id="a76d7-170">Niejawne konwersje dopuszczające wartość null</span><span class="sxs-lookup"><span data-stu-id="a76d7-170">Implicit nullable conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-nullable-conversions)
- [<span data-ttu-id="a76d7-171">Jawne konwersje dopuszczające wartość null</span><span class="sxs-lookup"><span data-stu-id="a76d7-171">Explicit nullable conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-nullable-conversions)
- [<span data-ttu-id="a76d7-172">Przenoszone operatory konwersji</span><span class="sxs-lookup"><span data-stu-id="a76d7-172">Lifted conversion operators</span></span>](~/_csharplang/spec/conversions.md#lifted-conversion-operators)

## <a name="see-also"></a><span data-ttu-id="a76d7-173">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a76d7-173">See also</span></span>

- [<span data-ttu-id="a76d7-174">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="a76d7-174">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a76d7-175">Co dokładnie ma znaczenie "zniesione"?</span><span class="sxs-lookup"><span data-stu-id="a76d7-175">What exactly does 'lifted' mean?</span></span>](/archive/blogs/ericlippert/what-exactly-does-lifted-mean)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
- <xref:System.Nullable.GetUnderlyingType%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a76d7-176">Typy referencyjne dopuszczające wartość null</span><span class="sxs-lookup"><span data-stu-id="a76d7-176">Nullable reference types</span></span>](nullable-reference-types.md)
