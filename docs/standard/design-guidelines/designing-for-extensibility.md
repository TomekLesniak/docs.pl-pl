---
title: Projektowanie pod kątem rozszerzalności
ms.date: 10/22/2008
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: 9e75ef433f3bd9af34e8dd40331a8267755e59fe
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821388"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="101c3-102">Projektowanie pod kątem rozszerzalności</span><span class="sxs-lookup"><span data-stu-id="101c3-102">Designing for Extensibility</span></span>
<span data-ttu-id="101c3-103">Jednym z ważniejszych aspektów projektowania struktury jest upewnienie się, że rozszerzalność struktury jest starannie rozpatrywana.</span><span class="sxs-lookup"><span data-stu-id="101c3-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="101c3-104">Wymaga to zrozumienia kosztów i korzyści związanych z różnymi mechanizmami rozszerzalności.</span><span class="sxs-lookup"><span data-stu-id="101c3-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="101c3-105">Ten rozdział ułatwia podjęcie decyzji, które mechanizmy rozszerzalności — podklasy, zdarzenia, wirtualne elementy członkowskie, wywołania zwrotne i tak dalej — mogą najlepiej spełniać wymagania platformy.</span><span class="sxs-lookup"><span data-stu-id="101c3-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="101c3-106">Istnieje wiele sposobów na umożliwienie rozszerzalności w strukturach.</span><span class="sxs-lookup"><span data-stu-id="101c3-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="101c3-107">Są one większe niż tańsze, ale tańsze, ale kosztowne.</span><span class="sxs-lookup"><span data-stu-id="101c3-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="101c3-108">W przypadku danego wymagania dotyczącego rozszerzalności należy wybrać najniższy, kosztowny mechanizm rozszerzania spełniający wymagania.</span><span class="sxs-lookup"><span data-stu-id="101c3-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="101c3-109">Należy pamiętać, że jest zwykle możliwe dodanie większej liczby rozszerzeń później, ale nigdy nie należy wprowadzać zmian.</span><span class="sxs-lookup"><span data-stu-id="101c3-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="101c3-110">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="101c3-110">In This Section</span></span>  
 [<span data-ttu-id="101c3-111">Niezapieczętowane klasy</span><span class="sxs-lookup"><span data-stu-id="101c3-111">Unsealed Classes</span></span>](unsealed-classes.md)  
 [<span data-ttu-id="101c3-112">Chronione elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="101c3-112">Protected Members</span></span>](protected-members.md)  
 [<span data-ttu-id="101c3-113">Zdarzenia i wywołania zwrotne</span><span class="sxs-lookup"><span data-stu-id="101c3-113">Events and Callbacks</span></span>](events-and-callbacks.md)  
 [<span data-ttu-id="101c3-114">Wirtualne elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="101c3-114">Virtual Members</span></span>](virtual-members.md)  
 [<span data-ttu-id="101c3-115">Abstrakcje (Typy abstrakcyjne i interfejsy)</span><span class="sxs-lookup"><span data-stu-id="101c3-115">Abstractions (Abstract Types and Interfaces)</span></span>](abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="101c3-116">Klasy podstawowe do implementowania streszczeń</span><span class="sxs-lookup"><span data-stu-id="101c3-116">Base Classes for Implementing Abstractions</span></span>](base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="101c3-117">Pieczętowanie</span><span class="sxs-lookup"><span data-stu-id="101c3-117">Sealing</span></span>](sealing.md)  
 <span data-ttu-id="101c3-118">*Fragmenty © 2005, 2009 Microsoft Corporation. Wszelkie prawa zastrzeżone.*</span><span class="sxs-lookup"><span data-stu-id="101c3-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="101c3-119">*Ponownie Wydrukowano przez uprawnienie Pearson Education, Inc. z [wytycznych dotyczących projektowania platformy: konwencje, idiomy i wzorce dla bibliotek .NET do wielokrotnego użytku, 2. wydanie](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) przez Krzysztof Cwalina i Brad Abrams, opublikowane 22, 2008 przez Addison-Wesley Professional w ramach serii Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="101c3-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="101c3-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="101c3-120">See also</span></span>

- [<span data-ttu-id="101c3-121">Wskazówki dotyczące projektowania struktury</span><span class="sxs-lookup"><span data-stu-id="101c3-121">Framework Design Guidelines</span></span>](index.md)
