---
title: Zbyt wielu klientów aplikacji DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
ms.openlocfilehash: dcac2658b18b753166770ba5b67024fe88b78b45
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078427"
---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="6998e-102">Zbyt wielu klientów aplikacji DLL</span><span class="sxs-lookup"><span data-stu-id="6998e-102">Too many DLL application clients</span></span>

<span data-ttu-id="6998e-103">Biblioteka dołączana dynamicznie (DLL) dla Visual Basic może obsługiwać dostęp tylko przez ograniczoną liczbę aplikacji hosta.</span><span class="sxs-lookup"><span data-stu-id="6998e-103">The dynamic-link library (DLL) for Visual Basic can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="6998e-104">Aplikacja i inne aplikacje, które są Visual Basic hosty (niektóre są dostępne dla aplikacji), próbują uzyskać dostęp do Visual Basic DLL w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="6998e-104">Your application and other applications that are Visual Basic hosts (some of which may be accessed by your application) are all attempting to access the Visual Basic DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6998e-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="6998e-105">To correct this error</span></span>  
  
- <span data-ttu-id="6998e-106">Zmniejsz liczbę otwartych aplikacji uzyskujących dostęp do Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6998e-106">Reduce the number of open applications accessing Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6998e-107">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6998e-107">See also</span></span>

- [<span data-ttu-id="6998e-108">Typy błędów</span><span class="sxs-lookup"><span data-stu-id="6998e-108">Error Types</span></span>](../programming-guide/language-features/error-types.md)
