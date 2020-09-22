---
title: Klasy pochodne nie mogą wywoływać zdarzeń klasy bazowej
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0233a1584c5e871506b5c4762e98874c343f19b8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874487"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="27b22-102">Klasy pochodne nie mogą wywoływać zdarzeń klasy bazowej</span><span class="sxs-lookup"><span data-stu-id="27b22-102">Derived classes cannot raise base class events</span></span>

<span data-ttu-id="27b22-103">Zdarzenie może być zgłaszane tylko z przestrzeni deklaracji, w której jest zadeklarowany.</span><span class="sxs-lookup"><span data-stu-id="27b22-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="27b22-104">W związku z tym Klasa nie może wywoływać zdarzeń z żadnej innej klasy, nawet jednego z nich, z której pochodzą.</span><span class="sxs-lookup"><span data-stu-id="27b22-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="27b22-105">**Identyfikator błędu:** BC30029</span><span class="sxs-lookup"><span data-stu-id="27b22-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="27b22-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="27b22-106">To correct this error</span></span>  
  
- <span data-ttu-id="27b22-107">Przenieś `Event` instrukcję lub `RaiseEvent` instrukcję tak, aby znajdowały się w tej samej klasie.</span><span class="sxs-lookup"><span data-stu-id="27b22-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27b22-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="27b22-108">See also</span></span>

- [<span data-ttu-id="27b22-109">Event — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="27b22-109">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="27b22-110">RaiseEvent — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="27b22-110">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
