---
title: Jak jawnie zaimplementować członków dwóch interfejsów — Przewodnik programowania w języku C#
description: Dowiedz się, jak jawnie zaimplementować dwa interfejsy, które mają te same nazwy elementów członkowskich i nadaj każdemu członkowi interfejsu osobną implementację w tym przykładzie w języku C#.
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 18b1f9cfb1690d35c0bca0a3c79c1b80ae5dd44d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205090"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="03831-103">Jak jawnie zaimplementować członków dwóch interfejsów (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="03831-103">How to explicitly implement members of two interfaces (C# Programming Guide)</span></span>

<span data-ttu-id="03831-104">Implementacja [interfejsu](../../language-reference/keywords/interface.md) jawnego pozwala programistom zaimplementować dwa interfejsy, które mają te same nazwy elementów członkowskich i nadać każdemu elementowi członkowskiemu interfejsu oddzielną implementację.</span><span class="sxs-lookup"><span data-stu-id="03831-104">Explicit [interface](../../language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="03831-105">W tym przykładzie wyświetlane są wymiary pola zarówno w jednostkach metrycznych, jak i w języku angielskim.</span><span class="sxs-lookup"><span data-stu-id="03831-105">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="03831-106">[Klasa](../../language-reference/keywords/class.md) Box implementuje dwa interfejsy IEnglishDimensions i IMetricDimensions, które reprezentują różne systemy pomiarowe.</span><span class="sxs-lookup"><span data-stu-id="03831-106">The Box [class](../../language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="03831-107">Oba interfejsy mają identyczne nazwy składowych, długość i szerokość.</span><span class="sxs-lookup"><span data-stu-id="03831-107">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03831-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="03831-108">Example</span></span>  

 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="03831-109">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="03831-109">Robust Programming</span></span>  

 <span data-ttu-id="03831-110">Jeśli chcesz wprowadzić wartości domyślne w jednostkach w języku angielskim, zaimplementuj normalne wartości długości i szerokości, a następnie jawnie Zaimplementuj metody długości i szerokości z interfejsu IMetricDimensions:</span><span class="sxs-lookup"><span data-stu-id="03831-110">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="03831-111">W takim przypadku można uzyskać dostęp do jednostek w języku angielskim z wystąpienia klasy i uzyskać dostęp do jednostek metryk z wystąpienia interfejsu:</span><span class="sxs-lookup"><span data-stu-id="03831-111">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="03831-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="03831-112">See also</span></span>

- [<span data-ttu-id="03831-113">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="03831-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="03831-114">Klasy i struktury</span><span class="sxs-lookup"><span data-stu-id="03831-114">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="03831-115">Interfejsy</span><span class="sxs-lookup"><span data-stu-id="03831-115">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="03831-116">Jawne implementowanie elementów interfejsu</span><span class="sxs-lookup"><span data-stu-id="03831-116">How to explicitly implement interface members</span></span>](./how-to-explicitly-implement-interface-members.md)
