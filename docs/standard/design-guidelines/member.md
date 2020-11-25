---
title: Składowa — zalecenia dotyczące projektowania
description: Poznaj wskazówki dotyczące projektowania członków w programie .NET. Elementy członkowskie obejmują metody, właściwości, zdarzenia, konstruktory i pola.
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
ms.openlocfilehash: 5070f45beccd89d6f051f1b1d8345390e915d471
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706596"
---
# <a name="member-design-guidelines"></a><span data-ttu-id="3abe9-104">Składowa — zalecenia dotyczące projektowania</span><span class="sxs-lookup"><span data-stu-id="3abe9-104">Member Design Guidelines</span></span>

<span data-ttu-id="3abe9-105">Metody, właściwości, zdarzenia, konstruktory i pola są zbiorczo nazywane elementami członkowskimi.</span><span class="sxs-lookup"><span data-stu-id="3abe9-105">Methods, properties, events, constructors, and fields are collectively referred to as members.</span></span> <span data-ttu-id="3abe9-106">Członkowie są ostatecznie sposobem, przez który funkcje platformy są udostępniane użytkownikom końcowym struktury.</span><span class="sxs-lookup"><span data-stu-id="3abe9-106">Members are ultimately the means by which framework functionality is exposed to the end users of a framework.</span></span>  
  
 <span data-ttu-id="3abe9-107">Elementy członkowskie mogą być wirtualne lub niewirtualne, konkretne lub abstrakcyjne, statyczne lub wystąpienia oraz mogą mieć kilka różnych zakresów ułatwień dostępu.</span><span class="sxs-lookup"><span data-stu-id="3abe9-107">Members can be virtual or nonvirtual, concrete or abstract, static or instance, and can have several different scopes of accessibility.</span></span> <span data-ttu-id="3abe9-108">Cała ta odmiana zawiera niesamowitą wyrazistości, ale w tym samym czasie wymaga zaopieki nad częścią projektanta struktury.</span><span class="sxs-lookup"><span data-stu-id="3abe9-108">All this variety provides incredible expressiveness but at the same time requires care on the part of the framework designer.</span></span>  
  
 <span data-ttu-id="3abe9-109">Ten rozdział zawiera podstawowe wytyczne, które należy stosować podczas projektowania członków dowolnego typu.</span><span class="sxs-lookup"><span data-stu-id="3abe9-109">This chapter offers basic guidelines that should be followed when designing members of any type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3abe9-110">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="3abe9-110">In This Section</span></span>  

 [<span data-ttu-id="3abe9-111">Przeciążenie elementu członkowskiego</span><span class="sxs-lookup"><span data-stu-id="3abe9-111">Member Overloading</span></span>](member-overloading.md)  
 [<span data-ttu-id="3abe9-112">Projekt właściwości</span><span class="sxs-lookup"><span data-stu-id="3abe9-112">Property Design</span></span>](property.md)  
 [<span data-ttu-id="3abe9-113">Projekt konstruktora</span><span class="sxs-lookup"><span data-stu-id="3abe9-113">Constructor Design</span></span>](constructor.md)  
 [<span data-ttu-id="3abe9-114">Projekt zdarzenia</span><span class="sxs-lookup"><span data-stu-id="3abe9-114">Event Design</span></span>](event.md)  
 [<span data-ttu-id="3abe9-115">Projekt pola</span><span class="sxs-lookup"><span data-stu-id="3abe9-115">Field Design</span></span>](field.md)  
 [<span data-ttu-id="3abe9-116">Metody rozszerzeń</span><span class="sxs-lookup"><span data-stu-id="3abe9-116">Extension Methods</span></span>](extension-methods.md)  
 [<span data-ttu-id="3abe9-117">Przeciążenia operatorów</span><span class="sxs-lookup"><span data-stu-id="3abe9-117">Operator Overloads</span></span>](operator-overloads.md)  
 [<span data-ttu-id="3abe9-118">Projekt parametru</span><span class="sxs-lookup"><span data-stu-id="3abe9-118">Parameter Design</span></span>](parameter-design.md)  
 <span data-ttu-id="3abe9-119">*Fragmenty © 2005, 2009 Microsoft Corporation. Wszelkie prawa zastrzeżone.*</span><span class="sxs-lookup"><span data-stu-id="3abe9-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3abe9-120">*Ponownie Wydrukowano przez uprawnienie Pearson Education, Inc. z [wytycznych dotyczących projektowania platformy: konwencje, idiomy i wzorce dla bibliotek .NET do wielokrotnego użytku, 2. wydanie](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) przez Krzysztof Cwalina i Brad Abrams, opublikowane 22, 2008 przez Addison-Wesley Professional w ramach serii Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="3abe9-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3abe9-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3abe9-121">See also</span></span>

- [<span data-ttu-id="3abe9-122">Wskazówki dotyczące projektowania struktury</span><span class="sxs-lookup"><span data-stu-id="3abe9-122">Framework Design Guidelines</span></span>](index.md)
