---
title: wyrażenia wartości domyślnych — odwołanie w C#
description: Użyj wyrażeń wartości domyślnych, aby uzyskać wartość domyślną typu
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
- default
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: f03971efa87bf03967c79512e44d22134dd80c17
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916870"
---
# <a name="default-value-expressions-c-reference"></a><span data-ttu-id="91f6c-103">wyrażenia wartości domyślnych (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="91f6c-103">default value expressions (C# reference)</span></span>

<span data-ttu-id="91f6c-104">Domyślne wyrażenie wartości generuje [wartość domyślną](../builtin-types/default-values.md) typu.</span><span class="sxs-lookup"><span data-stu-id="91f6c-104">A default value expression produces the [default value](../builtin-types/default-values.md) of a type.</span></span> <span data-ttu-id="91f6c-105">Istnieją dwa rodzaje wyrażeń wartości domyślnych: [domyślnego wywołania operatora](#default-operator) i [domyślnego literału](#default-literal).</span><span class="sxs-lookup"><span data-stu-id="91f6c-105">There are two kinds of default value expressions: the [default operator](#default-operator) call and a [default literal](#default-literal).</span></span>

<span data-ttu-id="91f6c-106">Możesz również użyć `default` słowa kluczowego jako domyślnej etykiety case w [ `switch` instrukcji](../keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="91f6c-106">You also use the `default` keyword as the default case label within a [`switch` statement](../keywords/switch.md).</span></span>

## <a name="default-operator"></a><span data-ttu-id="91f6c-107">default, operator</span><span class="sxs-lookup"><span data-stu-id="91f6c-107">default operator</span></span>

<span data-ttu-id="91f6c-108">Argument `default` operatora musi być nazwą typu lub parametrem typu, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="91f6c-108">The argument to the `default` operator must be the name of a type or a type parameter, as the following example shows:</span></span>

[!code-csharp-interactive[default of T](snippets/shared/DefaultOperator.cs#WithOperand)]

## <a name="default-literal"></a><span data-ttu-id="91f6c-109">domyślny literał</span><span class="sxs-lookup"><span data-stu-id="91f6c-109">default literal</span></span>

<span data-ttu-id="91f6c-110">Począwszy od języka C# 7,1, można użyć `default` literału, aby utworzyć wartość domyślną typu, gdy kompilator może wywnioskować typ wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="91f6c-110">Beginning with C# 7.1, you can use the `default` literal to produce the default value of a type when the compiler can infer the expression type.</span></span> <span data-ttu-id="91f6c-111">`default`Wyrażenie literału zwraca tę samą wartość, co `default(T)` wyrażenie, gdzie `T` jest typem wywnioskowanym.</span><span class="sxs-lookup"><span data-stu-id="91f6c-111">The `default` literal expression produces the same value as the `default(T)` expression where `T` is the inferred type.</span></span> <span data-ttu-id="91f6c-112">Literału można użyć `default` w dowolnym z następujących przypadków:</span><span class="sxs-lookup"><span data-stu-id="91f6c-112">You can use the `default` literal in any of the following cases:</span></span>

- <span data-ttu-id="91f6c-113">W przypisaniu lub inicjacji zmiennej.</span><span class="sxs-lookup"><span data-stu-id="91f6c-113">In the assignment or initialization of a variable.</span></span>
- <span data-ttu-id="91f6c-114">W deklaracji wartości domyślnej dla [opcjonalnego parametru metody](../../methods.md#optional-parameters-and-arguments).</span><span class="sxs-lookup"><span data-stu-id="91f6c-114">In the declaration of the default value for an [optional method parameter](../../methods.md#optional-parameters-and-arguments).</span></span>
- <span data-ttu-id="91f6c-115">W wywołaniu metody, aby podać wartość argumentu.</span><span class="sxs-lookup"><span data-stu-id="91f6c-115">In a method call to provide an argument value.</span></span>
- <span data-ttu-id="91f6c-116">W [ `return` instrukcji](../keywords/return.md) lub jako wyrażenie w [składowej](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)zawierającej wyrażenie.</span><span class="sxs-lookup"><span data-stu-id="91f6c-116">In a [`return` statement](../keywords/return.md) or as an expression in an [expression-bodied member](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

<span data-ttu-id="91f6c-117">W poniższym przykładzie pokazano użycie `default` literału:</span><span class="sxs-lookup"><span data-stu-id="91f6c-117">The following example shows the usage of the `default` literal:</span></span>

[!code-csharp-interactive[default literal](snippets/shared/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a><span data-ttu-id="91f6c-118">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="91f6c-118">C# language specification</span></span>

<span data-ttu-id="91f6c-119">Aby uzyskać więcej informacji, zobacz sekcję [wyrażenia wartości domyślnej](~/_csharplang/spec/expressions.md#default-value-expressions) [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="91f6c-119">For more information, see the [Default value expressions](~/_csharplang/spec/expressions.md#default-value-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="91f6c-120">Aby uzyskać więcej informacji na temat `default` literału, zapoznaj się z [uwagami](~/_csharplang/proposals/csharp-7.1/target-typed-default.md)dotyczącymi funkcji.</span><span class="sxs-lookup"><span data-stu-id="91f6c-120">For more information about the `default` literal, see the [feature proposal note](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="91f6c-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="91f6c-121">See also</span></span>

- [<span data-ttu-id="91f6c-122">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="91f6c-122">C# reference</span></span>](../index.md)
- [<span data-ttu-id="91f6c-123">Operatory i wyrażenia języka C#</span><span class="sxs-lookup"><span data-stu-id="91f6c-123">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="91f6c-124">Wartości domyślne typów C#</span><span class="sxs-lookup"><span data-stu-id="91f6c-124">Default values of C# types</span></span>](../builtin-types/default-values.md)
- [<span data-ttu-id="91f6c-125">Typy ogólne w .NET</span><span class="sxs-lookup"><span data-stu-id="91f6c-125">Generics in .NET</span></span>](../../../standard/generics/index.md)
