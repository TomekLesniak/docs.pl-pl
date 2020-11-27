---
title: Wywołania zakończone niepowodzeniami na sekundę
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: d3eafc4b31f0e62093a972b7c9f2325a3648d21b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285463"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="eacb1-102">Wywołania zakończone niepowodzeniami na sekundę</span><span class="sxs-lookup"><span data-stu-id="eacb1-102">Calls Failed Per Second</span></span>

<span data-ttu-id="eacb1-103">Nazwa licznika: wywołania zakończone niepowodzeniem na sekundę</span><span class="sxs-lookup"><span data-stu-id="eacb1-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="eacb1-104">Opis</span><span class="sxs-lookup"><span data-stu-id="eacb1-104">Description</span></span>  

 <span data-ttu-id="eacb1-105">Liczba wywołań z nieobsługiwanymi wyjątkami w tej operacji w drugim.</span><span class="sxs-lookup"><span data-stu-id="eacb1-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="eacb1-106">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="eacb1-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="eacb1-107">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="eacb1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="eacb1-108">Licznik jest zwiększany za każdym razem, gdy w tej operacji występuje nieobsługiwany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="eacb1-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eacb1-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="eacb1-109">See also</span></span>

- [<span data-ttu-id="eacb1-110">Określanie i obsługa błędów w kontraktach i usługach</span><span class="sxs-lookup"><span data-stu-id="eacb1-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
