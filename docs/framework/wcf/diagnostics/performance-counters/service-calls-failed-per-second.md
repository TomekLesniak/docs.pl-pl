---
title: 'Usługa: Wywołania zakończone niepowodzeniami na sekundę'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: c97e4b0c6c2c71756a9bed7b1a2359ad0c118a98
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252975"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="118b1-102">Usługa: Wywołania zakończone niepowodzeniami na sekundę</span><span class="sxs-lookup"><span data-stu-id="118b1-102">Service: Calls Failed Per Second</span></span>

<span data-ttu-id="118b1-103">Nazwa licznika: wywołania zakończone niepowodzeniem na sekundę.</span><span class="sxs-lookup"><span data-stu-id="118b1-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="118b1-104">Opis</span><span class="sxs-lookup"><span data-stu-id="118b1-104">Description</span></span>  

 <span data-ttu-id="118b1-105">Liczba wywołań, które mają Nieobsłużone wyjątki i są odbierane przez tę usługę w drugim.</span><span class="sxs-lookup"><span data-stu-id="118b1-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="118b1-106">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="118b1-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="118b1-107">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="118b1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="118b1-108">W kodzie zarządzanym wyjątki są generowane, gdy wystąpią błędy.</span><span class="sxs-lookup"><span data-stu-id="118b1-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="118b1-109">W kodzie zarządzanym wyjątki są generowane, gdy wystąpią błędy.</span><span class="sxs-lookup"><span data-stu-id="118b1-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="118b1-110">Licznik jest zwiększany za każdym razem, gdy w tej usłudze występuje nieobsługiwany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="118b1-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="118b1-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="118b1-111">See also</span></span>

- [<span data-ttu-id="118b1-112">Określanie i obsługa błędów w kontraktach i usługach</span><span class="sxs-lookup"><span data-stu-id="118b1-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
