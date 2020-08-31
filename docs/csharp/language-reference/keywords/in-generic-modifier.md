---
description: in (modyfikator ogólny) — odwołanie w C#
title: in (modyfikator ogólny) — odwołanie w C#
ms.date: 07/20/2015
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.openlocfilehash: feae17be7bdf29f6bc90e8c85b3878d4714699f4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118458"
---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="ba15a-103">in (modyfikator ogólny) (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="ba15a-103">in (Generic Modifier) (C# Reference)</span></span>

<span data-ttu-id="ba15a-104">W przypadku parametrów typu ogólnego `in` słowo kluczowe Określa, że parametr typu jest kontrawariantne.</span><span class="sxs-lookup"><span data-stu-id="ba15a-104">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="ba15a-105">Możesz użyć `in` słowa kluczowego w interfejsach ogólnych i delegatach.</span><span class="sxs-lookup"><span data-stu-id="ba15a-105">You can use the `in` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="ba15a-106">Kontrawariancja umożliwia użycie mniej pochodnego typu niż określony przez parametr generyczny.</span><span class="sxs-lookup"><span data-stu-id="ba15a-106">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="ba15a-107">Pozwala to na niejawną konwersję klas, które implementują interfejsy kontrawariantne i niejawną konwersję typów delegatów.</span><span class="sxs-lookup"><span data-stu-id="ba15a-107">This allows for implicit conversion of classes that implement contravariant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="ba15a-108">W przypadku typów referencyjnych są obsługiwane Kowariancja i kontrawariancja w parametrach typu ogólnego, ale nie są one obsługiwane w przypadku typów wartości.</span><span class="sxs-lookup"><span data-stu-id="ba15a-108">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="ba15a-109">Typ może być zadeklarowany jako kontrawariantne w ogólnym interfejsie lub delegatze tylko wtedy, gdy definiuje typ parametrów metody, a nie typ zwracany metody.</span><span class="sxs-lookup"><span data-stu-id="ba15a-109">A type can be declared contravariant in a generic interface or delegate only if it defines the type of a method's parameters and not of a method's return type.</span></span> <span data-ttu-id="ba15a-110">`In``ref`Parametry, i `out` muszą być niezmienne, co oznacza, że nie są one ani współvariant ani kontrawariantne.</span><span class="sxs-lookup"><span data-stu-id="ba15a-110">`In`, `ref`, and `out` parameters must be invariant, meaning they are neither covariant or contravariant.</span></span>

<span data-ttu-id="ba15a-111">Interfejs, który ma parametr typu kontrawariantne, umożliwia jej metodom akceptowanie argumentów o mniejszych typach pochodnych niż te określone przez parametr typu interfejsu.</span><span class="sxs-lookup"><span data-stu-id="ba15a-111">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="ba15a-112">Na przykład, w <xref:System.Collections.Generic.IComparer%601> interfejsie, wpisz T to kontrawariantne, można przypisać obiekt `IComparer<Person>` typu do obiektu `IComparer<Employee>` typu bez użycia żadnych specjalnych metod konwersji, jeśli `Employee` dziedziczy `Person` .</span><span class="sxs-lookup"><span data-stu-id="ba15a-112">For example, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer<Person>` type to an object of the `IComparer<Employee>` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>

<span data-ttu-id="ba15a-113">Delegatowi kontrawariantne można przypisać inny delegat tego samego typu, ale przy użyciu mniej pochodnego parametru typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="ba15a-113">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>

<span data-ttu-id="ba15a-114">Aby uzyskać więcej informacji, zobacz [Kowariancja i kontrawariancja](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="ba15a-114">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="contravariant-generic-interface"></a><span data-ttu-id="ba15a-115">Kontrawariantne — interfejs ogólny</span><span class="sxs-lookup"><span data-stu-id="ba15a-115">Contravariant generic interface</span></span>

<span data-ttu-id="ba15a-116">Poniższy przykład pokazuje, jak zadeklarować, zwiększyć i zaimplementować interfejs ogólny kontrawariantne.</span><span class="sxs-lookup"><span data-stu-id="ba15a-116">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="ba15a-117">Pokazano również, jak można użyć niejawnej konwersji dla klas implementujących ten interfejs.</span><span class="sxs-lookup"><span data-stu-id="ba15a-117">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>

[!code-csharp[csVarianceKeywords#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#1)]

## <a name="contravariant-generic-delegate"></a><span data-ttu-id="ba15a-118">Delegat ogólny kontrawariantne</span><span class="sxs-lookup"><span data-stu-id="ba15a-118">Contravariant generic delegate</span></span>

<span data-ttu-id="ba15a-119">Poniższy przykład pokazuje, jak zadeklarować, utworzyć wystąpienie i wywołać delegata generycznego kontrawariantne.</span><span class="sxs-lookup"><span data-stu-id="ba15a-119">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="ba15a-120">Pokazuje również, jak można niejawnie skonwertować typ delegata.</span><span class="sxs-lookup"><span data-stu-id="ba15a-120">It also shows how you can implicitly convert a delegate type.</span></span>

[!code-csharp[csVarianceKeywords#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="ba15a-121">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="ba15a-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ba15a-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ba15a-122">See also</span></span>

- [<span data-ttu-id="ba15a-123">określoną</span><span class="sxs-lookup"><span data-stu-id="ba15a-123">out</span></span>](out-generic-modifier.md)
- [<span data-ttu-id="ba15a-124">Kowariancja i kontrawariancja</span><span class="sxs-lookup"><span data-stu-id="ba15a-124">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="ba15a-125">Modyfikatory</span><span class="sxs-lookup"><span data-stu-id="ba15a-125">Modifiers</span></span>](index.md)
