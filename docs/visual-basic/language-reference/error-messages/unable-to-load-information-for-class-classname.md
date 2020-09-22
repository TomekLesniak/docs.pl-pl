---
title: Nie można załadować informacji dla klasy „<classname>”
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: 449bd34d5026dd4f9b9020123b99df81081f4331
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873511"
---
# <a name="unable-to-load-information-for-class-classname"></a><span data-ttu-id="89f1f-102">Nie można załadować informacji dla klasy „\<classname>”</span><span class="sxs-lookup"><span data-stu-id="89f1f-102">Unable to load information for class '\<classname>'</span></span>

<span data-ttu-id="89f1f-103">Wykonano odwołanie do klasy, która jest niedostępna.</span><span class="sxs-lookup"><span data-stu-id="89f1f-103">A reference was made to a class that is not available.</span></span>  
  
 <span data-ttu-id="89f1f-104">**Identyfikator błędu:** BC30712</span><span class="sxs-lookup"><span data-stu-id="89f1f-104">**Error ID:** BC30712</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="89f1f-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="89f1f-105">To correct this error</span></span>  
  
1. <span data-ttu-id="89f1f-106">Sprawdź, czy Klasa jest zdefiniowana i czy nazwa została wpisana poprawnie.</span><span class="sxs-lookup"><span data-stu-id="89f1f-106">Verify that the class is defined and that you spelled the name correctly.</span></span>  
  
2. <span data-ttu-id="89f1f-107">Spróbuj uzyskać dostęp do jednego z elementów członkowskich zadeklarowanych w module.</span><span class="sxs-lookup"><span data-stu-id="89f1f-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="89f1f-108">W niektórych przypadkach środowisko debugowania nie może zlokalizować elementów członkowskich, ponieważ moduły, w których są zadeklarowane, nie zostały jeszcze załadowane.</span><span class="sxs-lookup"><span data-stu-id="89f1f-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f1f-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="89f1f-109">See also</span></span>

- [<span data-ttu-id="89f1f-110">Debugowanie w Visual Studio</span><span class="sxs-lookup"><span data-stu-id="89f1f-110">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
