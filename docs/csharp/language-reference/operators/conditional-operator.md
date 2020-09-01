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
# <a name="-operator-c-reference"></a><span data-ttu-id="931a8-103">?: — operator (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="931a8-103">?: operator (C# reference)</span></span>

<span data-ttu-id="931a8-104">Operator warunkowy `?:` , znany również jako operator warunkowy Trzyelementowy, oblicza wyrażenie logiczne i zwraca wynik jednego z dwóch wyrażeń, w zależności od tego, czy wyrażenie logiczne oblicza wartość `true` lub `false` .</span><span class="sxs-lookup"><span data-stu-id="931a8-104">The conditional operator `?:`, also known as the ternary conditional operator, evaluates a Boolean expression and returns the result of one of the two expressions, depending on whether the Boolean expression evaluates to `true` or `false`.</span></span>

<span data-ttu-id="931a8-105">Składnia operatora warunkowego jest następująca:</span><span class="sxs-lookup"><span data-stu-id="931a8-105">The syntax for the conditional operator is as follows:</span></span>

```csharp
condition ? consequent : alternative
```

<span data-ttu-id="931a8-106">`condition`Wyrażenie musi być szacowane do `true` lub `false` .</span><span class="sxs-lookup"><span data-stu-id="931a8-106">The `condition` expression must evaluate to `true` or `false`.</span></span> <span data-ttu-id="931a8-107">Jeśli `condition` jest wynikiem obliczenia `true` , `consequent` wyrażenie jest oceniane, a jego wynik zmieni się na wynik operacji.</span><span class="sxs-lookup"><span data-stu-id="931a8-107">If `condition` evaluates to `true`, the `consequent` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="931a8-108">Jeśli `condition` jest wynikiem obliczenia `false` , `alternative` wyrażenie jest oceniane, a jego wynik zmieni się na wynik operacji.</span><span class="sxs-lookup"><span data-stu-id="931a8-108">If `condition` evaluates to `false`, the `alternative` expression is evaluated, and its result becomes the result of the operation.</span></span> <span data-ttu-id="931a8-109">Tylko `consequent` lub `alternative` jest oceniane.</span><span class="sxs-lookup"><span data-stu-id="931a8-109">Only `consequent` or `alternative` is evaluated.</span></span>

<span data-ttu-id="931a8-110">Typ `consequent` i `alternative` musi być taki sam lub musi być niejawną konwersją z jednego typu na drugi.</span><span class="sxs-lookup"><span data-stu-id="931a8-110">The type of `consequent` and `alternative` must be the same, or there must be an implicit conversion from one type to the other.</span></span>

<span data-ttu-id="931a8-111">Operator warunkowy jest prawym przyciskiem asocjacyjnym, czyli wyrażeniem formularza</span><span class="sxs-lookup"><span data-stu-id="931a8-111">The conditional operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ? b : c ? d : e
```

<span data-ttu-id="931a8-112">jest oceniane jako</span><span class="sxs-lookup"><span data-stu-id="931a8-112">is evaluated as</span></span>

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> <span data-ttu-id="931a8-113">Poniższego urządzenia można użyć do zapamiętania, jak jest oceniany operator warunkowy:</span><span class="sxs-lookup"><span data-stu-id="931a8-113">You can use the following mnemonic device to remember how the conditional operator is evaluated:</span></span>
>
> ```text
> is this condition true ? yes : no
> ```

<span data-ttu-id="931a8-114">Poniższy przykład ilustruje użycie operatora warunkowego:</span><span class="sxs-lookup"><span data-stu-id="931a8-114">The following example demonstrates the usage of the conditional operator:</span></span>

[!code-csharp-interactive[non ref conditional](snippets/shared/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a><span data-ttu-id="931a8-115">Wyrażenie warunkowe ref</span><span class="sxs-lookup"><span data-stu-id="931a8-115">Conditional ref expression</span></span>

<span data-ttu-id="931a8-116">Począwszy od języka C# 7,2, [lokalna](../keywords/ref.md#ref-locals) zmienna lokalna lub [ref tylko do odczytu](../keywords/ref.md#ref-readonly-locals) można przypisać warunkowo warunkowo wyrażenie ref.</span><span class="sxs-lookup"><span data-stu-id="931a8-116">Beginning with C# 7.2, a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable can be assigned conditionally with the conditional ref expression.</span></span> <span data-ttu-id="931a8-117">Można również użyć wyrażenia ref warunkowego jako [wartości zwracanej przez odwołanie](../keywords/ref.md#reference-return-values) lub jako [ `ref` argumentu metody](../keywords/ref.md#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="931a8-117">You can also use the conditional ref expression as a [reference return value](../keywords/ref.md#reference-return-values) or as a [`ref` method argument](../keywords/ref.md#passing-an-argument-by-reference).</span></span>

<span data-ttu-id="931a8-118">Składnia wyrażenia ref warunkowego jest następująca:</span><span class="sxs-lookup"><span data-stu-id="931a8-118">The syntax for the conditional ref expression is as follows:</span></span>

```csharp
condition ? ref consequent : ref alternative
```

<span data-ttu-id="931a8-119">Podobnie jak w przypadku oryginalnego operatora warunkowego wyrażenie ref oblicza tylko jedno z dwóch wyrażeń: albo `consequent` lub `alternative` .</span><span class="sxs-lookup"><span data-stu-id="931a8-119">Like the original conditional operator, the conditional ref expression evaluates only one of the two expressions: either `consequent` or `alternative`.</span></span>

<span data-ttu-id="931a8-120">W przypadku warunkowego wyrażenia ref typ `consequent` i `alternative` musi być taki sam.</span><span class="sxs-lookup"><span data-stu-id="931a8-120">In the case of the conditional ref expression, the type of `consequent` and `alternative` must be the same.</span></span>

<span data-ttu-id="931a8-121">Poniższy przykład demonstruje użycie warunkowego wyrażenia ref:</span><span class="sxs-lookup"><span data-stu-id="931a8-121">The following example demonstrates the usage of the conditional ref expression:</span></span>

[!code-csharp-interactive[conditional ref](snippets/shared/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a><span data-ttu-id="931a8-122">Operator warunkowy i `if..else` instrukcja</span><span class="sxs-lookup"><span data-stu-id="931a8-122">Conditional operator and an `if..else` statement</span></span>

<span data-ttu-id="931a8-123">Użycie operatora warunkowego zamiast instrukcji [if-else](../keywords/if-else.md) może spowodować bardziej zwięzły kod w przypadkach, gdy konieczne jest warunkowe obliczenie wartości.</span><span class="sxs-lookup"><span data-stu-id="931a8-123">Use of the conditional operator instead of an [if-else](../keywords/if-else.md) statement might result in more concise code in cases when you need conditionally to compute a value.</span></span> <span data-ttu-id="931a8-124">Poniższy przykład ilustruje dwa sposoby klasyfikowania liczby całkowitej jako ujemnej lub nieujemnej:</span><span class="sxs-lookup"><span data-stu-id="931a8-124">The following example demonstrates two ways to classify an integer as negative or nonnegative:</span></span>

[!code-csharp[conditional and if-else](snippets/shared/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a><span data-ttu-id="931a8-125">Przeciążanie operatora</span><span class="sxs-lookup"><span data-stu-id="931a8-125">Operator overloadability</span></span>

<span data-ttu-id="931a8-126">Typ zdefiniowany przez użytkownika nie może przeciążać operatora warunkowego.</span><span class="sxs-lookup"><span data-stu-id="931a8-126">A user-defined type cannot overload the conditional operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="931a8-127">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="931a8-127">C# language specification</span></span>

<span data-ttu-id="931a8-128">Aby uzyskać więcej informacji, zobacz sekcję [warunkowego operatora](~/_csharplang/spec/expressions.md#conditional-operator) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="931a8-128">For more information, see the [Conditional operator](~/_csharplang/spec/expressions.md#conditional-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="931a8-129">Aby uzyskać więcej informacji na temat wyrażenia ref warunkowego, zobacz [Uwaga dotycząca oferty funkcji](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span><span class="sxs-lookup"><span data-stu-id="931a8-129">For more information about the conditional ref expression, see the [feature proposal note](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="931a8-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="931a8-130">See also</span></span>

- [<span data-ttu-id="931a8-131">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="931a8-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="931a8-132">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="931a8-132">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="931a8-133">if-else, instrukcja</span><span class="sxs-lookup"><span data-stu-id="931a8-133">if-else statement</span></span>](../keywords/if-else.md)
- <span data-ttu-id="931a8-134">[?. lub? operator []](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="931a8-134">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="931a8-135">?? i? = — Operatory</span><span class="sxs-lookup"><span data-stu-id="931a8-135">?? and ??= operators</span></span>](null-coalescing-operator.md)
- [<span data-ttu-id="931a8-136">ref — słowo kluczowe</span><span class="sxs-lookup"><span data-stu-id="931a8-136">ref keyword</span></span>](../keywords/ref.md)
