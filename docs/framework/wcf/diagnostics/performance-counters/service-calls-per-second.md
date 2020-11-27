---
title: 'Usługa: Wywołania na sekundę'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: 7e702d402909c4a85a2cb42c837e0813c4d9f841
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252884"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="7e081-102">Usługa: Wywołania na sekundę</span><span class="sxs-lookup"><span data-stu-id="7e081-102">Service: Calls Per Second</span></span>

<span data-ttu-id="7e081-103">Nazwa licznika: wywołania na sekundę.</span><span class="sxs-lookup"><span data-stu-id="7e081-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7e081-104">Opis</span><span class="sxs-lookup"><span data-stu-id="7e081-104">Description</span></span>  

 <span data-ttu-id="7e081-105">Liczba wywołań tej usługi w drugim.</span><span class="sxs-lookup"><span data-stu-id="7e081-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="7e081-106">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="7e081-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="7e081-107">(N 1-N 0)/((D 1-D 0)/F) gdzie licznik (N) reprezentuje liczbę operacji wykonanych w ciągu ostatniego interwału próbkowania, mianownik (D) reprezentuje liczbę taktów, które upłynęły podczas ostatniego interwału próbkowania, a F jest częstotliwością taktów.</span><span class="sxs-lookup"><span data-stu-id="7e081-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
