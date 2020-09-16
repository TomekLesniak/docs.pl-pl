---
title: Nieautoryzowane wywołania zabezpieczeń na sekundę
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
ms.openlocfilehash: 8aed9f6b8c60c8aecd1b576c13a7063e3a492046
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552508"
---
# <a name="security-calls-not-authorized-per-second"></a><span data-ttu-id="6e805-102">Nieautoryzowane wywołania zabezpieczeń na sekundę</span><span class="sxs-lookup"><span data-stu-id="6e805-102">Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="6e805-103">Nazwa licznika: wywołania zabezpieczeń nie są autoryzowane na sekundę.</span><span class="sxs-lookup"><span data-stu-id="6e805-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6e805-104">Opis</span><span class="sxs-lookup"><span data-stu-id="6e805-104">Description</span></span>  
 <span data-ttu-id="6e805-105">Liczba wywołań, których autoryzacja zakończyła się niepowodzeniem w ramach tej operacji w drugim.</span><span class="sxs-lookup"><span data-stu-id="6e805-105">Number of calls that failed authorization in this operation in a second.</span></span>  
  
 <span data-ttu-id="6e805-106">Licznik jest zwiększany, gdy <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> Metoda zwraca `false` .</span><span class="sxs-lookup"><span data-stu-id="6e805-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="6e805-107">Wskazuje on, że komunikat przychodzący jest prawidłowym użytkownikiem i chroniony prawidłowo, ale użytkownik nie ma uprawnień do wykonywania określonych zadań.</span><span class="sxs-lookup"><span data-stu-id="6e805-107">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="6e805-108">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="6e805-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="6e805-109">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="6e805-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
