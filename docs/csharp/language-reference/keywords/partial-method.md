---
description: Metoda częściowa — odwołanie w C#
title: Metoda częściowa — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: d6c433fd30f6ec51355bdefee90d815783487c1b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134383"
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="40677-103">Metoda częściowa (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="40677-103">partial method (C# Reference)</span></span>

<span data-ttu-id="40677-104">Metoda częściowa ma swój podpis zdefiniowany w jednej części typu częściowego i jego implementacja zdefiniowana w innej części typu.</span><span class="sxs-lookup"><span data-stu-id="40677-104">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="40677-105">Metody częściowe umożliwiają projektantom klas dostarczanie punktów zaczepienia metody, podobnie jak procedury obsługi zdarzeń, które deweloperzy mogą zdecydować się na wdrożenie lub nie.</span><span class="sxs-lookup"><span data-stu-id="40677-105">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="40677-106">Jeśli deweloper nie poda implementacji, kompilator usuwa sygnaturę w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="40677-106">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="40677-107">Poniższe warunki dotyczą metod częściowych:</span><span class="sxs-lookup"><span data-stu-id="40677-107">The following conditions apply to partial methods:</span></span>

- <span data-ttu-id="40677-108">Sygnatury w obu częściach typu częściowego muszą być zgodne.</span><span class="sxs-lookup"><span data-stu-id="40677-108">Signatures in both parts of the partial type must match.</span></span>

- <span data-ttu-id="40677-109">Metoda musi zwracać typ void.</span><span class="sxs-lookup"><span data-stu-id="40677-109">The method must return void.</span></span>

- <span data-ttu-id="40677-110">Modyfikatory dostępu nie są dozwolone.</span><span class="sxs-lookup"><span data-stu-id="40677-110">No access modifiers are allowed.</span></span> <span data-ttu-id="40677-111">Metody częściowe są niejawnie prywatne.</span><span class="sxs-lookup"><span data-stu-id="40677-111">Partial methods are implicitly private.</span></span>

<span data-ttu-id="40677-112">Poniższy przykład przedstawia metodę częściową zdefiniowaną w dwóch częściach klasy częściowej:</span><span class="sxs-lookup"><span data-stu-id="40677-112">The following example shows a partial method defined in two parts of a partial class:</span></span>

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

<span data-ttu-id="40677-113">Aby uzyskać więcej informacji, zobacz [częściowe klasy i metody](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="40677-113">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="40677-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="40677-114">See also</span></span>

- [<span data-ttu-id="40677-115">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="40677-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="40677-116">Typ częściowy</span><span class="sxs-lookup"><span data-stu-id="40677-116">partial type</span></span>](partial-type.md)
