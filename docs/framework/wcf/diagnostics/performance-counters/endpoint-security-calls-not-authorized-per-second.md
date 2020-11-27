---
title: 'Punkt końcowy: wywołania zabezpieczeń bez autoryzacji na sekundę'
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
ms.openlocfilehash: 5b289d7e026b481576bd7de186364773a57c17bc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256524"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a><span data-ttu-id="df51d-102">Punkt końcowy: wywołania zabezpieczeń bez autoryzacji na sekundę</span><span class="sxs-lookup"><span data-stu-id="df51d-102">Endpoint: Security Calls Not Authorized Per Second</span></span>

<span data-ttu-id="df51d-103">Nazwa licznika: wywołania zabezpieczeń nie są autoryzowane na sekundę.</span><span class="sxs-lookup"><span data-stu-id="df51d-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="df51d-104">Opis</span><span class="sxs-lookup"><span data-stu-id="df51d-104">Description</span></span>  

 <span data-ttu-id="df51d-105">Liczba komunikatów przychodzących w drugim, które są prawidłowymi użytkownikami i są chronione prawidłowo, ale użytkownik nie ma uprawnień do wykonywania określonych zadań.</span><span class="sxs-lookup"><span data-stu-id="df51d-105">Number of incoming messages in a second that are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="df51d-106">Licznik jest zwiększany, gdy <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> Metoda zwraca `false` .</span><span class="sxs-lookup"><span data-stu-id="df51d-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="df51d-107">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="df51d-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="df51d-108">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="df51d-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
