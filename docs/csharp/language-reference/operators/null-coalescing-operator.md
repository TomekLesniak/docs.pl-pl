---
description: ?? i? = Operatory — odwołanie w C#
title: ?? i? = Operatory — odwołanie w C#
ms.date: 09/10/2019
f1_keywords:
- ??_CSharpKeyword
- ??=_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
- null-coalescing assignment [C#]
- ??= operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 273bc6d3a4c65c09dc600621b435bf0d1baea9e4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118289"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="249b6-105">??</span><span class="sxs-lookup"><span data-stu-id="249b6-105">??</span></span> <span data-ttu-id="249b6-106">i? = — Operatory (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="249b6-106">and ??= operators (C# reference)</span></span>

<span data-ttu-id="249b6-107">Operator łączenia wartości null `??` zwraca wartość operandu po lewej stronie, jeśli nie jest `null` ; w przeciwnym razie oblicza argument operacji po prawej stronie i zwraca wynik.</span><span class="sxs-lookup"><span data-stu-id="249b6-107">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="249b6-108">`??`Operator nie oblicza swojego operandu po prawej stronie, jeśli argument operacji po lewej stronie ma wartość różną od null.</span><span class="sxs-lookup"><span data-stu-id="249b6-108">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="249b6-109">W języku C# 8,0 i nowszych operator przypisania łączenia wartości null `??=` przypisuje wartość jego operandu po lewej stronie tylko wtedy, gdy argument operacji po lewej stronie jest obliczany do `null` .</span><span class="sxs-lookup"><span data-stu-id="249b6-109">Available in C# 8.0 and later, the null-coalescing assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="249b6-110">`??=`Operator nie oblicza swojego operandu po prawej stronie, jeśli argument operacji po lewej stronie ma wartość różną od null.</span><span class="sxs-lookup"><span data-stu-id="249b6-110">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

[!code-csharp[null-coalescing assignment](snippets/shared/NullCoalescingOperator.cs#Assignment)]

<span data-ttu-id="249b6-111">Argument operacji po lewej stronie `??=` operatora musi być zmienną, [właściwością](../../programming-guide/classes-and-structs/properties.md)lub elementem [indeksatora](../../programming-guide/indexers/index.md) .</span><span class="sxs-lookup"><span data-stu-id="249b6-111">The left-hand operand of the `??=` operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element.</span></span>

<span data-ttu-id="249b6-112">W języku C# 7,3 i starszych typ operandu po lewej stronie `??` operatora musi być typem [referencyjnym](../keywords/reference-types.md) lub [typem wartości null](../builtin-types/nullable-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="249b6-112">In C# 7.3 and earlier, the type of the left-hand operand of the `??` operator must be either a [reference type](../keywords/reference-types.md) or a [nullable value type](../builtin-types/nullable-value-types.md).</span></span> <span data-ttu-id="249b6-113">Począwszy od języka C# 8,0, ten wymóg jest zastępowany przez następujący: typ operandu po lewej stronie `??` `??=` operatora and nie może być typem wartości niedopuszczających wartości null.</span><span class="sxs-lookup"><span data-stu-id="249b6-113">Beginning with C# 8.0, that requirement is replaced with the following: the type of the left-hand operand of the `??` and `??=` operators cannot be a non-nullable value type.</span></span> <span data-ttu-id="249b6-114">W szczególności, począwszy od języka C# 8,0, można użyć operatorów łączenia wartości null z nieokreślonymi parametrami typu:</span><span class="sxs-lookup"><span data-stu-id="249b6-114">In particular, beginning with C# 8.0, you can use the null-coalescing operators with unconstrained type parameters:</span></span>

[!code-csharp[unconstrained type parameter](snippets/shared/NullCoalescingOperator.cs#UnconstrainedType)]

<span data-ttu-id="249b6-115">Operatory łączenia wartości null są z prawej strony skojarzenia.</span><span class="sxs-lookup"><span data-stu-id="249b6-115">The null-coalescing operators are right-associative.</span></span> <span data-ttu-id="249b6-116">To jest wyrażenie w postaci</span><span class="sxs-lookup"><span data-stu-id="249b6-116">That is, expressions of the form</span></span>

```csharp
a ?? b ?? c
d ??= e ??= f
```

<span data-ttu-id="249b6-117">są oceniane jako</span><span class="sxs-lookup"><span data-stu-id="249b6-117">are evaluated as</span></span>

```csharp
a ?? (b ?? c)
d ??= (e ??= f)
```

## <a name="examples"></a><span data-ttu-id="249b6-118">Przykłady</span><span class="sxs-lookup"><span data-stu-id="249b6-118">Examples</span></span>

<span data-ttu-id="249b6-119">`??`Operatory i `??=` mogą być przydatne w następujących scenariuszach:</span><span class="sxs-lookup"><span data-stu-id="249b6-119">The `??` and `??=` operators can be useful in the following scenarios:</span></span>

- <span data-ttu-id="249b6-120">W wyrażeniach zawierających [Operatory warunkowe o wartości null?. i? []](member-access-operators.md#null-conditional-operators--and-)można użyć `??` operatora, aby podać alternatywne wyrażenie do obliczenia w przypadku, gdy wynik wyrażenia z operacjami warunkowymi o wartości null jest `null` :</span><span class="sxs-lookup"><span data-stu-id="249b6-120">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the `??` operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](snippets/shared/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="249b6-121">Podczas pracy z [typami wartości null](../builtin-types/nullable-value-types.md) i musi podać wartość bazowego typu wartości, użyj `??` operatora, aby określić wartość, która ma zostać podana na wypadek, gdy wartość typu dopuszczająca wartości null to `null` :</span><span class="sxs-lookup"><span data-stu-id="249b6-121">When you work with [nullable value types](../builtin-types/nullable-value-types.md) and need to provide a value of an underlying value type, use the `??` operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](snippets/shared/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="249b6-122">Użyj <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> metody, jeśli wartość, która ma zostać użyta, gdy wartość typu dopuszczająca wartości null ma `null` być wartością domyślną dla bazowego typu wartości.</span><span class="sxs-lookup"><span data-stu-id="249b6-122">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="249b6-123">Począwszy od języka C# 7,0, można użyć [ `throw` wyrażenia](../keywords/throw.md#the-throw-expression) jako argumentu operacji po prawej stronie `??` operatora, aby kod sprawdzania argumentów był bardziej zwięzły:</span><span class="sxs-lookup"><span data-stu-id="249b6-123">Beginning with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the `??` operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](snippets/shared/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="249b6-124">W powyższym przykładzie pokazano również, jak używać [składowych wyrażeń](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) w celu zdefiniowania właściwości.</span><span class="sxs-lookup"><span data-stu-id="249b6-124">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

- <span data-ttu-id="249b6-125">Począwszy od języka C# 8,0, można użyć `??=` operatora, aby zamienić kod formularza</span><span class="sxs-lookup"><span data-stu-id="249b6-125">Beginning with C# 8.0, you can use the `??=` operator to replace the code of the form</span></span>

  ```csharp
  if (variable is null)
  {
      variable = expression;
  }
  ```

  <span data-ttu-id="249b6-126">przy użyciu następującego kodu:</span><span class="sxs-lookup"><span data-stu-id="249b6-126">with the following code:</span></span>

  ```csharp
  variable ??= expression;
  ```

## <a name="operator-overloadability"></a><span data-ttu-id="249b6-127">Przeciążanie operatora</span><span class="sxs-lookup"><span data-stu-id="249b6-127">Operator overloadability</span></span>

<span data-ttu-id="249b6-128">Operatory `??` i `??=` nie mogą być przeciążone.</span><span class="sxs-lookup"><span data-stu-id="249b6-128">The operators `??` and `??=` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="249b6-129">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="249b6-129">C# language specification</span></span>

<span data-ttu-id="249b6-130">Aby uzyskać więcej informacji na temat `??` operatora, zobacz sekcję [operator łączenia wartości null](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="249b6-130">For more information about the `??` operator, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="249b6-131">Aby uzyskać więcej informacji na temat `??=` operatora, zobacz [Uwaga dotycząca oferty funkcji](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span><span class="sxs-lookup"><span data-stu-id="249b6-131">For more information about the `??=` operator, see the [feature proposal note](~/_csharplang/proposals/csharp-8.0/null-coalescing-assignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="249b6-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="249b6-132">See also</span></span>

- [<span data-ttu-id="249b6-133">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="249b6-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="249b6-134">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="249b6-134">C# operators and expressions</span></span>](index.md)
- <span data-ttu-id="249b6-135">[?. lub? operator []](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="249b6-135">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="249b6-136">?: — operator</span><span class="sxs-lookup"><span data-stu-id="249b6-136">?: operator</span></span>](conditional-operator.md)
