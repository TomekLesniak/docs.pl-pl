---
description: Operatory przypisania — odwołanie w C#
title: Operatory przypisania — odwołanie w C#
ms.date: 09/10/2019
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 3df118143b692cc8655de31cce23af41f7da125c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89117886"
---
# <a name="assignment-operators-c-reference"></a><span data-ttu-id="5d6aa-103">Operatory przypisania (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="5d6aa-103">Assignment operators (C# reference)</span></span>

<span data-ttu-id="5d6aa-104">Operator przypisania `=` przypisuje wartość jego operandu po prawej stronie do zmiennej, [Właściwości](../../programming-guide/classes-and-structs/properties.md)lub elementu [indeksatora](../../programming-guide/indexers/index.md) podanym przez operand z lewej strony.</span><span class="sxs-lookup"><span data-stu-id="5d6aa-104">The assignment operator `=` assigns the value of its right-hand operand to a variable, a [property](../../programming-guide/classes-and-structs/properties.md), or an [indexer](../../programming-guide/indexers/index.md) element given by its left-hand operand.</span></span> <span data-ttu-id="5d6aa-105">Wynikiem wyrażenia przypisania jest wartość przypisana do operandu po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="5d6aa-105">The result of an assignment expression is the value assigned to the left-hand operand.</span></span> <span data-ttu-id="5d6aa-106">Typ operandu po prawej stronie musi być taki sam jak typ operandu po lewej stronie lub niejawnie konwertowany.</span><span class="sxs-lookup"><span data-stu-id="5d6aa-106">The type of the right-hand operand must be the same as the type of the left-hand operand or implicitly convertible to it.</span></span>

<span data-ttu-id="5d6aa-107">Operator przypisania `=` jest prawym przyciskiem asocjacyjnym, czyli wyrażeniem formularza</span><span class="sxs-lookup"><span data-stu-id="5d6aa-107">The assignment operator `=` is right-associative, that is, an expression of the form</span></span>

```csharp
a = b = c
```

<span data-ttu-id="5d6aa-108">jest oceniane jako</span><span class="sxs-lookup"><span data-stu-id="5d6aa-108">is evaluated as</span></span>

```csharp
a = (b = c)
```

<span data-ttu-id="5d6aa-109">Poniższy przykład ilustruje użycie operatora przypisania ze zmienną lokalną, właściwością i elementem indeksatora jako swój argument operacji po lewej stronie:</span><span class="sxs-lookup"><span data-stu-id="5d6aa-109">The following example demonstrates the usage of the assignment operator with a local variable, a property, and an indexer element as its left-hand operand:</span></span>

[!code-csharp-interactive[simple assignment](snippets/shared/AssignmentOperator.cs#Simple)]

## <a name="ref-assignment-operator"></a><span data-ttu-id="5d6aa-110">operator przypisania ref</span><span class="sxs-lookup"><span data-stu-id="5d6aa-110">ref assignment operator</span></span>

<span data-ttu-id="5d6aa-111">Począwszy od języka C# 7,3, można użyć operatora przypisania odwołania, `= ref` Aby ponownie przypisać [lokalną](../keywords/ref.md#ref-locals) zmienną lokalną lub [ref tylko do odczytu](../keywords/ref.md#ref-readonly-locals) .</span><span class="sxs-lookup"><span data-stu-id="5d6aa-111">Beginning with C# 7.3, you can use the ref assignment operator `= ref` to reassign a [ref local](../keywords/ref.md#ref-locals) or [ref readonly local](../keywords/ref.md#ref-readonly-locals) variable.</span></span> <span data-ttu-id="5d6aa-112">Poniższy przykład ilustruje użycie operatora przypisania odwołania:</span><span class="sxs-lookup"><span data-stu-id="5d6aa-112">The following example demonstrates the usage of the ref assignment operator:</span></span>

[!code-csharp[ref assignment operator](snippets/shared/AssignmentOperator.cs#RefAssignment)]

<span data-ttu-id="5d6aa-113">W przypadku operatora przypisania odwołania, oba operandy muszą być tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="5d6aa-113">In the case of the ref assignment operator, the both of its operands must be of the same type.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="5d6aa-114">Przypisanie złożone</span><span class="sxs-lookup"><span data-stu-id="5d6aa-114">Compound assignment</span></span>

<span data-ttu-id="5d6aa-115">Dla operatora binarnego `op` wyrażenie złożonego przypisania formularza</span><span class="sxs-lookup"><span data-stu-id="5d6aa-115">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="5d6aa-116">jest równoważny</span><span class="sxs-lookup"><span data-stu-id="5d6aa-116">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="5d6aa-117">z tą różnicą, że `x` jest obliczana tylko raz.</span><span class="sxs-lookup"><span data-stu-id="5d6aa-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="5d6aa-118">Przypisanie złożone jest obsługiwane przez [arytmetyczne](arithmetic-operators.md#compound-assignment)operatory [logiczne logiczne](boolean-logical-operators.md#compound-assignment) [i bitowe](bitwise-and-shift-operators.md#compound-assignment) .</span><span class="sxs-lookup"><span data-stu-id="5d6aa-118">Compound assignment is supported by [arithmetic](arithmetic-operators.md#compound-assignment), [Boolean logical](boolean-logical-operators.md#compound-assignment), and [bitwise logical and shift](bitwise-and-shift-operators.md#compound-assignment) operators.</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="5d6aa-119">Przypisanie do łączenia o wartości null</span><span class="sxs-lookup"><span data-stu-id="5d6aa-119">Null-coalescing assignment</span></span>

<span data-ttu-id="5d6aa-120">Począwszy od języka C# 8,0, można użyć operatora przypisania łączącego wartości null, `??=` Aby przypisać wartość jego operandu po lewej stronie tylko wtedy, gdy argument operacji po lewej stronie jest wynikiem `null` .</span><span class="sxs-lookup"><span data-stu-id="5d6aa-120">Beginning with C# 8.0, you can use the null-coalescing assignment operator `??=` to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span> <span data-ttu-id="5d6aa-121">Aby uzyskać więcej informacji, zobacz [? =](null-coalescing-operator.md) — artykuł.</span><span class="sxs-lookup"><span data-stu-id="5d6aa-121">For more information, see the [?? and ??= operators](null-coalescing-operator.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="5d6aa-122">Przeciążanie operatora</span><span class="sxs-lookup"><span data-stu-id="5d6aa-122">Operator overloadability</span></span>

<span data-ttu-id="5d6aa-123">Typ zdefiniowany przez użytkownika nie może [przeciążać](operator-overloading.md) operatora przypisania.</span><span class="sxs-lookup"><span data-stu-id="5d6aa-123">A user-defined type cannot [overload](operator-overloading.md) the assignment operator.</span></span> <span data-ttu-id="5d6aa-124">Jednak typ zdefiniowany przez użytkownika może definiować niejawną konwersję na inny typ.</span><span class="sxs-lookup"><span data-stu-id="5d6aa-124">However, a user-defined type can define an implicit conversion to another type.</span></span> <span data-ttu-id="5d6aa-125">W ten sposób wartość typu zdefiniowanego przez użytkownika może być przypisana do zmiennej, właściwości lub elementu indeksatora innego typu.</span><span class="sxs-lookup"><span data-stu-id="5d6aa-125">That way, the value of a user-defined type can be assigned to a variable, a property, or an indexer element of another type.</span></span> <span data-ttu-id="5d6aa-126">Aby uzyskać więcej informacji, zobacz [Operatory konwersji zdefiniowane przez użytkownika](user-defined-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="5d6aa-126">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

<span data-ttu-id="5d6aa-127">Typ zdefiniowany przez użytkownika nie może jawnie przeciążać złożonego operatora przypisania.</span><span class="sxs-lookup"><span data-stu-id="5d6aa-127">A user-defined type cannot explicitly overload a compound assignment operator.</span></span> <span data-ttu-id="5d6aa-128">Jeśli jednak typ zdefiniowany przez użytkownika przeciąża operator binarny, `op` `op=` operator (jeśli istnieje) jest również niejawnie przeciążony.</span><span class="sxs-lookup"><span data-stu-id="5d6aa-128">However, if a user-defined type overloads a binary operator `op`, the `op=` operator, if it exists, is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5d6aa-129">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="5d6aa-129">C# language specification</span></span>

<span data-ttu-id="5d6aa-130">Aby uzyskać więcej informacji, zobacz sekcję [Operatory przypisania](~/_csharplang/spec/expressions.md#assignment-operators) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="5d6aa-130">For more information, see the [Assignment operators](~/_csharplang/spec/expressions.md#assignment-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="5d6aa-131">Aby uzyskać więcej informacji na temat operatora przypisania odwołania `= ref` , zobacz [Uwaga dotycząca oferty funkcji](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span><span class="sxs-lookup"><span data-stu-id="5d6aa-131">For more information about the ref assignment operator `= ref`, see the [feature proposal note](~/_csharplang/proposals/csharp-7.3/ref-local-reassignment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d6aa-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5d6aa-132">See also</span></span>

- [<span data-ttu-id="5d6aa-133">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="5d6aa-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5d6aa-134">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="5d6aa-134">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="5d6aa-135">ref — słowo kluczowe</span><span class="sxs-lookup"><span data-stu-id="5d6aa-135">ref keyword</span></span>](../keywords/ref.md)
