---
description: New — odwołanie w C#
title: New — odwołanie w C#
ms.date: 10/02/2020
f1_keywords:
- new_CSharpKeyword
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 3125f3d2c694dcfc5682ee482f3f76072ac3726d
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609385"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="a3fe9-103">New — Operator (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="a3fe9-103">new operator (C# reference)</span></span>

<span data-ttu-id="a3fe9-104">`new`Operator tworzy nowe wystąpienie typu.</span><span class="sxs-lookup"><span data-stu-id="a3fe9-104">The `new` operator creates a new instance of a type.</span></span>

<span data-ttu-id="a3fe9-105">Można również użyć `new` słowa kluczowego jako [modyfikatora deklaracji składowej](../keywords/new-modifier.md) lub [ograniczenia typu ogólnego](../keywords/new-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="a3fe9-105">You can also use the `new` keyword as a [member declaration modifier](../keywords/new-modifier.md) or a [generic type constraint](../keywords/new-constraint.md).</span></span>

## <a name="constructor-invocation"></a><span data-ttu-id="a3fe9-106">Wywołanie konstruktora</span><span class="sxs-lookup"><span data-stu-id="a3fe9-106">Constructor invocation</span></span>

<span data-ttu-id="a3fe9-107">Aby utworzyć nowe wystąpienie typu, zazwyczaj wywoływany jest jeden z [konstruktorów](../../programming-guide/classes-and-structs/constructors.md) tego typu przy użyciu `new` operatora:</span><span class="sxs-lookup"><span data-stu-id="a3fe9-107">To create a new instance of a type, you typically invoke one of the [constructors](../../programming-guide/classes-and-structs/constructors.md) of that type using the `new` operator:</span></span>

[!code-csharp-interactive[invoke constructor](snippets/shared/NewOperator.cs#Constructor)]

<span data-ttu-id="a3fe9-108">Można użyć [inicjatora obiektu lub kolekcji](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) z `new` operatorem, aby utworzyć wystąpienie i zainicjować obiekt w jednej instrukcji, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="a3fe9-108">You can use an [object or collection initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) with the `new` operator to instantiate and initialize an object in one statement, as the following example shows:</span></span>

[!code-csharp-interactive[constructor with initializer](snippets/shared/NewOperator.cs#ConstructorWithInitializer)]

<span data-ttu-id="a3fe9-109">Począwszy od języka C# 9,0, wyrażenia wywołania konstruktora mają typ docelowy.</span><span class="sxs-lookup"><span data-stu-id="a3fe9-109">Beginning with C# 9.0, constructor invocation expressions are target-typed.</span></span> <span data-ttu-id="a3fe9-110">Oznacza to, że jeśli jest znany typ docelowy wyrażenia, można pominąć nazwę typu, jak pokazano na poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="a3fe9-110">That is, if a target type of an expression is known, you can omit a type name, as the following example shows:</span></span>

:::code language="csharp" source="snippets/shared/NewOperator.cs" id="SnippetTargetTyped":::

<span data-ttu-id="a3fe9-111">Jak pokazano w powyższym przykładzie, zawsze używaj nawiasów w wyrażeniu z typem docelowym `new` .</span><span class="sxs-lookup"><span data-stu-id="a3fe9-111">As the preceding example shows, you always use parentheses in a target-typed `new` expression.</span></span>

<span data-ttu-id="a3fe9-112">Jeśli typ docelowy `new` wyrażenia jest nieznany (na przykład w przypadku użycia [`var`](../keywords/var.md) słowa kluczowego), należy określić nazwę typu.</span><span class="sxs-lookup"><span data-stu-id="a3fe9-112">If a target type of a `new` expression is unknown (for example, when you use the [`var`](../keywords/var.md) keyword), you must specify a type name.</span></span>

## <a name="array-creation"></a><span data-ttu-id="a3fe9-113">Tworzenie tablicy</span><span class="sxs-lookup"><span data-stu-id="a3fe9-113">Array creation</span></span>

<span data-ttu-id="a3fe9-114">Możesz również użyć `new` operatora, aby utworzyć wystąpienie tablicy, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="a3fe9-114">You also use the `new` operator to create an array instance, as the following example shows:</span></span>

[!code-csharp-interactive[create array](snippets/shared/NewOperator.cs#Array)]

<span data-ttu-id="a3fe9-115">Użyj składni inicjowania tablicy, aby utworzyć wystąpienie tablicy i wypełnić je elementami w jednej instrukcji.</span><span class="sxs-lookup"><span data-stu-id="a3fe9-115">Use array initialization syntax to create an array instance and populate it with elements in one statement.</span></span> <span data-ttu-id="a3fe9-116">W poniższym przykładzie pokazano różne sposoby wykonywania następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="a3fe9-116">The following example shows various ways how you can do that:</span></span>

[!code-csharp-interactive[initialize array](snippets/shared/NewOperator.cs#ArrayInitialization)]

<span data-ttu-id="a3fe9-117">Aby uzyskać więcej informacji na temat tablic, zobacz [tablice](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="a3fe9-117">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="instantiation-of-anonymous-types"></a><span data-ttu-id="a3fe9-118">Tworzenie wystąpienia typów anonimowych</span><span class="sxs-lookup"><span data-stu-id="a3fe9-118">Instantiation of anonymous types</span></span>

<span data-ttu-id="a3fe9-119">Aby utworzyć wystąpienie [typu anonimowego](../../programming-guide/classes-and-structs/anonymous-types.md), użyj `new` składni operatora i inicjatora obiektów:</span><span class="sxs-lookup"><span data-stu-id="a3fe9-119">To create an instance of an [anonymous type](../../programming-guide/classes-and-structs/anonymous-types.md), use the `new` operator and object initializer syntax:</span></span>

[!code-csharp-interactive[anonymous type](snippets/shared/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a><span data-ttu-id="a3fe9-120">Niszczenie wystąpień typu</span><span class="sxs-lookup"><span data-stu-id="a3fe9-120">Destruction of type instances</span></span>

<span data-ttu-id="a3fe9-121">Nie trzeba zniszczyć wcześniej utworzonych wystąpień typu.</span><span class="sxs-lookup"><span data-stu-id="a3fe9-121">You don't have to destroy earlier created type instances.</span></span> <span data-ttu-id="a3fe9-122">Wystąpienia obu typów odwołań i wartości są niszczone automatycznie.</span><span class="sxs-lookup"><span data-stu-id="a3fe9-122">Instances of both reference and value types are destroyed automatically.</span></span> <span data-ttu-id="a3fe9-123">Wystąpienia typów wartości są niszczone, gdy tylko kontekst, który zawiera te elementy, zostanie zniszczony.</span><span class="sxs-lookup"><span data-stu-id="a3fe9-123">Instances of value types are destroyed as soon as the context that contains them is destroyed.</span></span> <span data-ttu-id="a3fe9-124">Wystąpienia typów odwołań są niszczone przez [Moduł wyrzucania elementów bezużytecznych](../../../standard/garbage-collection/index.md) w nieokreślonym czasie po usunięciu ostatniego odwołania do nich.</span><span class="sxs-lookup"><span data-stu-id="a3fe9-124">Instances of reference types are destroyed by the [garbage collector](../../../standard/garbage-collection/index.md) at some unspecified time after the last reference to them is removed.</span></span>

<span data-ttu-id="a3fe9-125">Dla wystąpień typu, które zawierają niezarządzane zasoby, na przykład dojście do pliku, zaleca się zapełnienie deterministycznym czyszczeniem, aby upewnić się, że zasoby, które zawierają, są wystawione tak szybko, jak to możliwe.</span><span class="sxs-lookup"><span data-stu-id="a3fe9-125">For type instances that contain unmanaged resources, for example, a file handle, it's recommended to employ deterministic clean-up to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="a3fe9-126">Aby uzyskać więcej informacji, zobacz <xref:System.IDisposable?displayProperty=nameWithType> Dokumentacja interfejsu API i artykuł [using instrukcji](../keywords/using-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="a3fe9-126">For more information, see the <xref:System.IDisposable?displayProperty=nameWithType> API reference and the [using statement](../keywords/using-statement.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="a3fe9-127">Przeciążanie operatora</span><span class="sxs-lookup"><span data-stu-id="a3fe9-127">Operator overloadability</span></span>

<span data-ttu-id="a3fe9-128">Typ zdefiniowany przez użytkownika nie może przeciążać `new` operatora.</span><span class="sxs-lookup"><span data-stu-id="a3fe9-128">A user-defined type cannot overload the `new` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a3fe9-129">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="a3fe9-129">C# language specification</span></span>

<span data-ttu-id="a3fe9-130">Aby uzyskać więcej informacji, zobacz sekcję [New Operator](~/_csharplang/spec/expressions.md#the-new-operator) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="a3fe9-130">For more information, see [The new operator](~/_csharplang/spec/expressions.md#the-new-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="a3fe9-131">Aby uzyskać więcej informacji na temat wyrażenia z określonym typem docelowym `new` , zobacz [Uwaga dotycząca oferty funkcji](~/_csharplang/proposals/csharp-9.0/target-typed-new.md).</span><span class="sxs-lookup"><span data-stu-id="a3fe9-131">For more information about a target-typed `new` expression, see the [feature proposal note](~/_csharplang/proposals/csharp-9.0/target-typed-new.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a3fe9-132">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a3fe9-132">See also</span></span>

- [<span data-ttu-id="a3fe9-133">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="a3fe9-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a3fe9-134">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="a3fe9-134">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="a3fe9-135">Inicjatory obiektów i kolekcji</span><span class="sxs-lookup"><span data-stu-id="a3fe9-135">Object and collection initializers</span></span>](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
