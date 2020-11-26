---
title: 'Usługa: Wywołania zabezpieczeń bez autoryzacji'
ms.date: 03/30/2017
ms.assetid: 3024b20a-5250-4bd1-a38c-c6d79f89610b
ms.openlocfilehash: 32b0a62ecf9364270f5580787b7e129af5ac80b2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236913"
---
# <a name="service-security-calls-not-authorized"></a><span data-ttu-id="ed5f2-102">Usługa: Wywołania zabezpieczeń bez autoryzacji</span><span class="sxs-lookup"><span data-stu-id="ed5f2-102">Service: Security Calls Not Authorized</span></span>

<span data-ttu-id="ed5f2-103">Nazwa licznika: wywołania zabezpieczeń nie są autoryzowane.</span><span class="sxs-lookup"><span data-stu-id="ed5f2-103">Counter Name: Security Calls Not Authorized.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ed5f2-104">Opis</span><span class="sxs-lookup"><span data-stu-id="ed5f2-104">Description</span></span>  

 <span data-ttu-id="ed5f2-105">Licznik jest zwiększany, gdy <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> Metoda zwraca `false` .</span><span class="sxs-lookup"><span data-stu-id="ed5f2-105">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="ed5f2-106">Wskazuje on, że komunikat przychodzący jest prawidłowym użytkownikiem i chroniony prawidłowo, ale użytkownik nie ma uprawnień do wykonywania określonych zadań.</span><span class="sxs-lookup"><span data-stu-id="ed5f2-106">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>
