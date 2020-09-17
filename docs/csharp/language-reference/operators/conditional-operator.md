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
# <a name="-operator-c-reference"></a><span data-ttu-id="aa6a4-103">?: — operator (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="aa6a4-103">?: operator (C# reference)</span></span>

<span data-ttu-id="aa6a4-104">Operator warunkowy `?:` , znany również jako operator warunkowy Trzyelementowy, oblicza wyrażenie logiczne i zwraca wynik jednego z dwóch wyrażeń, w zależności od tego, czy wyrażenie logiczne oblicza wartość `true` lub `false` .</span><span class="sxs-lookup"><span data-stu-id="aa6a4-104">The conditional operator `?:`, also known as the ternary conditional operator, evaluates a Boolean expression and returns the result of one of the two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span>

<span data-ttu-id="aa6a4-105">Składnia operatora warunkowego jest następująca:</span><span class="sxs-lookup"><span data-stu-id="aa6a4-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="aa6a4-106">`condition`Wyrażenie musi być szacowane do `true` lub `false` .</span><span class="sxs-lookup"><span data-stu-id="aa6a4-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="aa6a4-107">Jeśli `condition` jest wynikiem obliczenia `true` , `consequent` wyrażenie jest oceniane, a jego wynik zmieni się na wynik operacji.</span><span class="sxs-lookup"><span data-stu-id="aa6a4-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="aa6a4-108">Jeśli `condition` jest wynikiem obliczenia `false` , `alternative` wyrażenie jest oceniane, a jego wynik zmieni się na wynik operacji.</span><span class="sxs-lookup"><span data-stu-id="aa6a4-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="aa6a4-109">Tylko `consequent` lub `alternative` jest oceniane.</span><span class="sxs-lookup"><span data-stu-id="aa6a4-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="aa6a4-110">Począwszy od języka C# 9,0, wyrażenia warunkowe mają typ docelowy.</span><span class="sxs-lookup"><span data-stu-id="aa6a4-110">Beginning with C# 9.0, conditional expressions are target-typed.</span></span> <span data-ttu-id="aa6a4-111">Oznacza to, że jeśli jest znany typ docelowy wyrażenia warunkowego, typy `consequent` i `alternative` muszą być niejawnie konwertowane na typ docelowy, jak pokazano na poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="aa6a4-111">That is, if a target type of a conditional expression is known, the types of `consequent` and `alternative` must be implicitly convertible to the target type, as the following example shows:</span></span>

[!code-csharp[target-typed conditional](snippets/shared/ConditionalOperator.cs#TargetTyped)]

<span data-ttu-id="aa6a4-112">Jeśli typ docelowy wyrażenia warunkowego jest nieznany (na przykład w przypadku użycia [`var`](../keywords/var.md) słowa kluczowego) lub w języku C# 8,0 i starszych, typ `consequent` i `alternative` musi być taki sam lub musi być niejawną konwersją z jednego typu na drugi:</span><span class="sxs-lookup"><span data-stu-id="aa6a4-112">If a target type of a conditional expression is unknown (for example, when you use the [`var`](../keywords/var.md) keyword) or in C# 8.0 and earlier, the type of `consequent` and `alternative` must be the same or there must be an implicit conversion from one type to the other:</span></span>

[!code-csharp[not target-typed conditional](snippets/shared/ConditionalOperator.cs#NotTargetTyped)]

<span data-ttu-id="aa6a4-113">Operator warunkowy jest prawym przyciskiem asocjacyjnym, czyli wyrażeniem formularza</span><span class="sxs-lookup"><span data-stu-id="aa6a4-113">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="aa6a4-114">jest oceniane jako</span><span class="sxs-lookup"><span data-stu-id="aa6a4-114">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> <span data-ttu-id="aa6a4-115">Poniższego urządzenia można użyć do zapamiętania, jak jest oceniany operator warunkowy:</span><span class="sxs-lookup"><span data-stu-id="aa6a4-115">You can use the following mnemonic device to remember how the conditional operator is evaluated:</span></span>
>
> ```text
> is this condition true ? yes : no
> ```

<span data-ttu-id="aa6a4-116">Poniższy przykład ilustruje użycie operatora warunkowego:</span><span class="sxs-lookup"><span data-stu-id="aa6a4-116">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp-interactive[non ref conditional](snippets/shared/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="aa6a4-117">Wyrażenie warunkowe ref</span><span class="sxs-lookup"><span data-stu-id="aa6a4-117">Conditional ref expression</span></span>

<span data-ttu-id="aa6a4-118">Począwszy od języka C# 7,2, [lokalna](../keywords/ref.md#ref-locals) zmienna lokalna lub [ref tylko do odczytu](../keywords/ref.md#ref-readonly-locals) można przypisać warunkowo warunkowo wyrażenie ref.</span><span class="sxs-lookup"><span data-stu-id="aa6a4-118">Beginning with C# 7.2, a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable can be assigned conditionally with a conditional ref expression.</span></span> <span data-ttu-id="aa6a4-119">Można również użyć wyrażenia ref warunkowego jako [wartości zwracanej przez odwołanie](../keywords/ref.md#reference-return-values) lub jako [ `ref` argumentu metody](../keywords/ref.md#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="aa6a4-119">You can also use a conditional ref expression as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method argument](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="aa6a4-120">Składnia wyrażenia ref warunkowego jest następująca:</span><span class="sxs-lookup"><span data-stu-id="aa6a4-120">The syntax for a conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="aa6a4-121">Podobnie jak w przypadku oryginalnego operatora warunkowego wyrażenie ref oblicza tylko jedno z dwóch wyrażeń: albo `consequent` lub `alternative` .</span><span class="sxs-lookup"><span data-stu-id="aa6a4-121">Like the original conditional operator, a conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="aa6a4-122">W przypadku warunkowego wyrażenia ref typ `consequent` i `alternative` musi być taki sam.</span><span class="sxs-lookup"><span data-stu-id="aa6a4-122">In the case of a conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span> <span data-ttu-id="aa6a4-123">Wyrażenia referencyjne warunkowe nie są typami docelowymi.</span><span class="sxs-lookup"><span data-stu-id="aa6a4-123">Conditional ref expressions are not target-typed.</span></span>

<span data-ttu-id="aa6a4-124">Poniższy przykład demonstruje użycie warunkowego wyrażenia ref:</span><span class="sxs-lookup"><span data-stu-id="aa6a4-124">The following example demonstrates the usage of a conditional ref expression:</span></span>

[!code-csharp-interactive[conditional ref](snippets/shared/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="aa6a4-125">Operator warunkowy i `if..else` instrukcja</span><span class="sxs-lookup"><span data-stu-id="aa6a4-125">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="aa6a4-126">Użycie operatora warunkowego zamiast instrukcji [if-else](../keywords/if-else.md) może spowodować bardziej zwięzły kod w przypadkach, gdy konieczne jest warunkowe obliczenie wartości.</span><span class="sxs-lookup"><span data-stu-id="aa6a4-126">Use of the conditional operator instead of an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="aa6a4-127">Poniższy przykład ilustruje dwa sposoby klasyfikowania liczby całkowitej jako ujemnej lub nieujemnej:</span><span class="sxs-lookup"><span data-stu-id="aa6a4-127">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](snippets/shared/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="aa6a4-128">Przeciążanie operatora</span><span class="sxs-lookup"><span data-stu-id="aa6a4-128">Operator overloadability</span></span>

<span data-ttu-id="aa6a4-129">Typ zdefiniowany przez użytkownika nie może przeciążać operatora warunkowego.</span><span class="sxs-lookup"><span data-stu-id="aa6a4-129">A user-defined type cannot overload the conditional operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="aa6a4-130">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="aa6a4-130">C# language specification</span></span>

<span data-ttu-id="aa6a4-131">Aby uzyskać więcej informacji, zobacz sekcję [warunkowego operatora](~/_csharplang/spec/expressions.md#conditional-operator) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="aa6a4-131">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="aa6a4-132">Aby uzyskać więcej informacji na temat funkcji dodanych w języku C# 7,2 i nowszych, zobacz następujące uwagi dotyczące propozycji funkcji:</span><span class="sxs-lookup"><span data-stu-id="aa6a4-132">For more information about features added in C# 7.2 and later, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="aa6a4-133">Warunkowe wyrażenia ref (C# 7,2)</span><span class="sxs-lookup"><span data-stu-id="aa6a4-133">Conditional ref expressions (C# 7.2)</span></span>](~/_csharplang/proposals/csharp-7.2/conditional-ref.md)
- [<span data-ttu-id="aa6a4-134">Wyrażenie warunkowe o typie docelowym (C# 9,0)</span><span class="sxs-lookup"><span data-stu-id="aa6a4-134">Target-typed conditional expression (C# 9.0)</span></span>](~/_csharplang/proposals/csharp-9.0/target-typed-conditional-expression.md)

## <a name="see-also"></a><span data-ttu-id="aa6a4-135">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aa6a4-135">See also</span></span>

- [<span data-ttu-id="aa6a4-136">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="aa6a4-136">C# reference</span></span>](../index.md)
- [<span data-ttu-id="aa6a4-137">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="aa6a4-137">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="aa6a4-138">if-else, instrukcja</span><span class="sxs-lookup"><span data-stu-id="aa6a4-138">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="aa6a4-139">[?. lub? operator []](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="aa6a4-139">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="aa6a4-140">?? i? = — Operatory</span><span class="sxs-lookup"><span data-stu-id="aa6a4-140">?? and ??= operators</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="aa6a4-141">ref — słowo kluczowe</span><span class="sxs-lookup"><span data-stu-id="aa6a4-141">ref keyword</span></span>](../keywords/ref.md)
