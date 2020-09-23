---
title: Użycie domyślnego wystąpienia klasy w konstruktorze klas może prowadzić do nieskończonego wywołania cyklicznego
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: 5d239fdb7dcc5c488bf0341043b810ec7dadc083
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100324"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a><span data-ttu-id="64251-102">Użycie domyślnego wystąpienia klasy w konstruktorze klas może prowadzić do nieskończonego wywołania cyklicznego</span><span class="sxs-lookup"><span data-stu-id="64251-102">Use of Default Instance of a class in the class constructor could lead to infinite recursive call</span></span>

<span data-ttu-id="64251-103">W konstruktorze klasy użyto domyślnego wystąpienia klasy.</span><span class="sxs-lookup"><span data-stu-id="64251-103">A default instance of a class has been used in the constructor of the class.</span></span> <span data-ttu-id="64251-104">Może to prowadzić do nieskończonego wywołania cyklicznego, nazywanego również pętlą nieskończoną.</span><span class="sxs-lookup"><span data-stu-id="64251-104">This can lead to an infinite recursive call, also known as an infinite loop.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="64251-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="64251-105">To correct this error</span></span>  
  
- <span data-ttu-id="64251-106">Usuń wystąpienie domyślne z konstruktora klasy.</span><span class="sxs-lookup"><span data-stu-id="64251-106">Remove the default instance from the class constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64251-107">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="64251-107">See also</span></span>

- [<span data-ttu-id="64251-108">Konstruktory</span><span class="sxs-lookup"><span data-stu-id="64251-108">Constructors</span></span>](../programming-guide/concepts/object-oriented-programming.md#constructors)
