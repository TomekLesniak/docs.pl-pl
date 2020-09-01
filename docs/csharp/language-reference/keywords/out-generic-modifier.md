---
description: out — słowo kluczowe (modyfikator ogólny) — odwołanie w C#
title: out — słowo kluczowe (modyfikator ogólny) — odwołanie w C#
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
ms.openlocfilehash: 84f3647309c0772f6ae61d3614f8649fe277f153
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142339"
---
# <a name="out-generic-modifier-c-reference"></a><span data-ttu-id="5deeb-103">out (modyfikator ogólny) (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="5deeb-103">out (generic modifier) (C# Reference)</span></span>

<span data-ttu-id="5deeb-104">W przypadku parametrów typu ogólnego `out` słowo kluczowe Określa, że parametr typu jest współwariantem.</span><span class="sxs-lookup"><span data-stu-id="5deeb-104">For generic type parameters, the `out` keyword specifies that the type parameter is covariant.</span></span> <span data-ttu-id="5deeb-105">Możesz użyć `out` słowa kluczowego w interfejsach ogólnych i delegatach.</span><span class="sxs-lookup"><span data-stu-id="5deeb-105">You can use the `out` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="5deeb-106">Kowariancja umożliwia użycie bardziej pochodnego typu niż określony przez parametr generyczny.</span><span class="sxs-lookup"><span data-stu-id="5deeb-106">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="5deeb-107">Pozwala to na niejawną konwersję klas, które implementują interfejsy współwariantu i niejawną konwersję typów delegatów.</span><span class="sxs-lookup"><span data-stu-id="5deeb-107">This allows for implicit conversion of classes that implement covariant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="5deeb-108">Dla typów referencyjnych są obsługiwane Kowariancja i kontrawariancja, ale nie są one obsługiwane w przypadku typów wartości.</span><span class="sxs-lookup"><span data-stu-id="5deeb-108">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="5deeb-109">Interfejs, który ma parametr typu klasy współdzielonej, umożliwia jej metodom zwrócenie większej liczby typów pochodnych niż te określone przez parametr typu.</span><span class="sxs-lookup"><span data-stu-id="5deeb-109">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="5deeb-110">Na przykład, ponieważ w .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601> , typu T jest współwariantem, można przypisać obiekt `IEnumerable(Of String)` typu do obiektu `IEnumerable(Of Object)` typu bez użycia żadnych specjalnych metod konwersji.</span><span class="sxs-lookup"><span data-stu-id="5deeb-110">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerable(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>

<span data-ttu-id="5deeb-111">Delegata, do którego można przypisać inny delegat tego samego typu, ale z bardziej pochodnym parametrem typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="5deeb-111">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>

<span data-ttu-id="5deeb-112">Aby uzyskać więcej informacji, zobacz [Kowariancja i kontrawariancja](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="5deeb-112">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="example---covariant-generic-interface"></a><span data-ttu-id="5deeb-113">Przykład — interfejs ogólny typu "-Variant"</span><span class="sxs-lookup"><span data-stu-id="5deeb-113">Example - covariant generic interface</span></span>

<span data-ttu-id="5deeb-114">Poniższy przykład pokazuje, jak zadeklarować, zwiększyć i zaimplementować interfejs ogólny typu "współvariant".</span><span class="sxs-lookup"><span data-stu-id="5deeb-114">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="5deeb-115">Przedstawiono w nim również sposób użycia niejawnej konwersji dla klas, które implementują interfejs współvariant.</span><span class="sxs-lookup"><span data-stu-id="5deeb-115">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>

[!code-csharp[csVarianceKeywords#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#3)]

<span data-ttu-id="5deeb-116">W interfejsie ogólnym parametr typu może być zadeklarowany jako współwariant, jeśli spełnia następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="5deeb-116">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>

- <span data-ttu-id="5deeb-117">Parametr typu jest używany tylko jako typ zwracany metod interfejsu i nie jest używany jako typ argumentów metody.</span><span class="sxs-lookup"><span data-stu-id="5deeb-117">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5deeb-118">Istnieje jeden wyjątek dla tej reguły.</span><span class="sxs-lookup"><span data-stu-id="5deeb-118">There is one exception to this rule.</span></span> <span data-ttu-id="5deeb-119">Jeśli w interfejsie o niezmiennym jest kontrawariantne delegat generyczny jako parametr metody, można użyć typu współwariantu jako parametru typu ogólnego dla tego delegata.</span><span class="sxs-lookup"><span data-stu-id="5deeb-119">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="5deeb-120">Aby uzyskać więcej informacji na temat elementów delegowanych i kontrawariantne ogólnych, zobacz [Wariancja w delegatach](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) i [Używanie wariancji dla delegatów typu Func i akcja](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="5deeb-120">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

- <span data-ttu-id="5deeb-121">Parametr typu nie jest używany jako ograniczenie ogólne metod interfejsu.</span><span class="sxs-lookup"><span data-stu-id="5deeb-121">The type parameter is not used as a generic constraint for the interface methods.</span></span>

## <a name="example---covariant-generic-delegate"></a><span data-ttu-id="5deeb-122">Przykład — delegat generyczny ogólny</span><span class="sxs-lookup"><span data-stu-id="5deeb-122">Example - covariant generic delegate</span></span>

<span data-ttu-id="5deeb-123">Poniższy przykład pokazuje, jak zadeklarować, utworzyć wystąpienie i wywołać delegata ogólnego typu.</span><span class="sxs-lookup"><span data-stu-id="5deeb-123">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="5deeb-124">Pokazuje również, jak niejawnie skonwertować typy delegatów.</span><span class="sxs-lookup"><span data-stu-id="5deeb-124">It also shows how to implicitly convert delegate types.</span></span>

[!code-csharp[csVarianceKeywords#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#4)]

<span data-ttu-id="5deeb-125">W delegatze ogólnym typ może być zadeklarowany jako współwariant, jeśli jest używany tylko jako zwracany typ metody i nie jest używany dla argumentów metody.</span><span class="sxs-lookup"><span data-stu-id="5deeb-125">In a generic delegate, a type can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5deeb-126">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="5deeb-126">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5deeb-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5deeb-127">See also</span></span>

- [<span data-ttu-id="5deeb-128">Wariancje w interfejsach</span><span class="sxs-lookup"><span data-stu-id="5deeb-128">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="5deeb-129">podczas</span><span class="sxs-lookup"><span data-stu-id="5deeb-129">in</span></span>](in-generic-modifier.md)
- [<span data-ttu-id="5deeb-130">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="5deeb-130">Modifiers</span></span>](index.md)
