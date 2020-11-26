---
title: 'Usługa: Nieautoryzowane wywołania zabezpieczeń na sekundę'
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
ms.openlocfilehash: db9e333f740f19e4f82ea0f1306a11e6c21ba996
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236926"
---
# <a name="service-security-calls-not-authorized-per-second"></a><span data-ttu-id="f7ae8-102">Usługa: Nieautoryzowane wywołania zabezpieczeń na sekundę</span><span class="sxs-lookup"><span data-stu-id="f7ae8-102">Service: Security Calls Not Authorized Per Second</span></span>

<span data-ttu-id="f7ae8-103">Nazwa licznika: wywołania zabezpieczeń bez autoryzacji na sekundę</span><span class="sxs-lookup"><span data-stu-id="f7ae8-103">Counter name: Security Calls Not Authorized Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="f7ae8-104">Opis</span><span class="sxs-lookup"><span data-stu-id="f7ae8-104">Description</span></span>  

 <span data-ttu-id="f7ae8-105">Liczba wiadomości przychodzących w jednej sekund, które są od prawidłowego użytkownika i są chronione prawidłowo, ale użytkownik nie ma uprawnień do wykonywania określonych zadań.</span><span class="sxs-lookup"><span data-stu-id="f7ae8-105">Number of incoming messages in one second, which are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="f7ae8-106">Licznik jest zwiększany, gdy <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> Metoda zwraca `false` .</span><span class="sxs-lookup"><span data-stu-id="f7ae8-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="f7ae8-107">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="f7ae8-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="f7ae8-108">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="f7ae8-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
