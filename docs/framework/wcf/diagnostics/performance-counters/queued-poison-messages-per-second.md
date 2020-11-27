---
title: Zakolejkowane komunikaty zanieczyszczone na sekundę
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: 1e515a81580bd9773841bee4230288d8c7d12216
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276233"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="fc161-102">Zakolejkowane komunikaty zanieczyszczone na sekundę</span><span class="sxs-lookup"><span data-stu-id="fc161-102">Queued Poison Messages Per Second</span></span>

<span data-ttu-id="fc161-103">Nazwa licznika: skażone komunikaty w kolejce na sekundę.</span><span class="sxs-lookup"><span data-stu-id="fc161-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="fc161-104">Opis</span><span class="sxs-lookup"><span data-stu-id="fc161-104">Description</span></span>  

 <span data-ttu-id="fc161-105">Liczba komunikatów oznaczonych jako skażone przez transport w kolejce w tej usłudze w drugim.</span><span class="sxs-lookup"><span data-stu-id="fc161-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="fc161-106">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="fc161-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="fc161-107">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="fc161-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
