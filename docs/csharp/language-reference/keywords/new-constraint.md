---
description: nowe ograniczenie — odwołanie w C#
title: nowe ograniczenie — odwołanie w C#
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: f7b097729fe973aba7b85c48e1b1033aade83080
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139453"
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="ee870-103">New — ograniczenie (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="ee870-103">new constraint (C# Reference)</span></span>

<span data-ttu-id="ee870-104">`new`Ograniczenie określa, że argument typu w deklaracji klasy ogólnej musi mieć publiczny Konstruktor bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="ee870-104">The `new` constraint specifies that a type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="ee870-105">Aby użyć `new` ograniczenia, typ nie może być abstrakcyjny.</span><span class="sxs-lookup"><span data-stu-id="ee870-105">To use the `new` constraint, the type cannot be abstract.</span></span>

<span data-ttu-id="ee870-106">Zastosuj `new` ograniczenie do parametru typu, gdy Klasa ogólna tworzy nowe wystąpienia typu, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="ee870-106">Apply the `new` constraint to a type parameter when a generic class creates new instances of the type, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

<span data-ttu-id="ee870-107">W przypadku użycia `new()` ograniczenia z innymi ograniczeniami należy je określić Last:</span><span class="sxs-lookup"><span data-stu-id="ee870-107">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

<span data-ttu-id="ee870-108">Aby uzyskać więcej informacji, zobacz [ograniczenia dotyczące parametrów typu](../../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="ee870-108">For more information, see [Constraints on Type Parameters](../../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="ee870-109">Możesz również użyć `new` słowa kluczowego, aby [utworzyć wystąpienie typu](../operators/new-operator.md) lub jako [modyfikator deklaracji składowej](new-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="ee870-109">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [member declaration modifier](new-modifier.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ee870-110">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="ee870-110">C# language specification</span></span>

<span data-ttu-id="ee870-111">Aby uzyskać więcej informacji, zobacz sekcję [ograniczenia parametrów typu](~/_csharplang/spec/classes.md#type-parameter-constraints) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="ee870-111">For more information, see the [Type parameter constraints](~/_csharplang/spec/classes.md#type-parameter-constraints) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ee870-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ee870-112">See also</span></span>

- [<span data-ttu-id="ee870-113">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="ee870-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ee870-114">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="ee870-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ee870-115">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="ee870-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ee870-116">Typy ogólne</span><span class="sxs-lookup"><span data-stu-id="ee870-116">Generics</span></span>](../../programming-guide/generics/index.md)
