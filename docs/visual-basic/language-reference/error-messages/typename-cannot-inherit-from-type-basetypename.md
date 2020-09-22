---
title: Element „<typename>” nie może dziedziczyć po elemencie <type> „<basetypename>", ponieważ rozszerza dostęp podstawowego elementu <type> poza zestawem
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 5adb5a74c220c7b2f95ac7370040a7fa2bd34299
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872061"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="ff59e-102">Element „\<typename>” nie może dziedziczyć po elemencie \<type> „\<basetypename>", ponieważ rozszerza dostęp podstawowego elementu \<type> poza zestawem</span><span class="sxs-lookup"><span data-stu-id="ff59e-102">'\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>

<span data-ttu-id="ff59e-103">Klasa lub interfejs dziedziczy z klasy bazowej lub interfejsu, ale ma mniej restrykcyjny poziom dostępu.</span><span class="sxs-lookup"><span data-stu-id="ff59e-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="ff59e-104">Na przykład `Public` interfejs dziedziczy z `Friend` interfejsu lub `Protected` Klasa dziedziczy z `Private` klasy.</span><span class="sxs-lookup"><span data-stu-id="ff59e-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="ff59e-105">To ujawnia klasę bazową lub interfejs, aby uzyskać dostęp poza zaplanowanym poziomem.</span><span class="sxs-lookup"><span data-stu-id="ff59e-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="ff59e-106">**Identyfikator błędu:** BC30910</span><span class="sxs-lookup"><span data-stu-id="ff59e-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ff59e-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="ff59e-107">To correct this error</span></span>  
  
- <span data-ttu-id="ff59e-108">Zmień poziom dostępu klasy pochodnej lub interfejsu na co najmniej jako restrykcyjny dla klasy bazowej lub interfejsu.</span><span class="sxs-lookup"><span data-stu-id="ff59e-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="ff59e-109">-lub-</span><span class="sxs-lookup"><span data-stu-id="ff59e-109">-or-</span></span>  
  
- <span data-ttu-id="ff59e-110">Jeśli potrzebujesz mniej restrykcyjnego poziomu dostępu, Usuń `Inherits` instrukcję.</span><span class="sxs-lookup"><span data-stu-id="ff59e-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="ff59e-111">Nie można dziedziczyć z bardziej ograniczonej klasy bazowej lub interfejsu.</span><span class="sxs-lookup"><span data-stu-id="ff59e-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff59e-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ff59e-112">See also</span></span>

- [<span data-ttu-id="ff59e-113">Class, instrukcja</span><span class="sxs-lookup"><span data-stu-id="ff59e-113">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="ff59e-114">Interface, instrukcja</span><span class="sxs-lookup"><span data-stu-id="ff59e-114">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="ff59e-115">Inherits — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="ff59e-115">Inherits Statement</span></span>](../statements/inherits-statement.md)
- [<span data-ttu-id="ff59e-116">Poziomy dostępu w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff59e-116">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
