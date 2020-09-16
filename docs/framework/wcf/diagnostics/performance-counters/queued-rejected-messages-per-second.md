---
title: Zakolejkowane komunikaty odrzucone na sekundę
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 5ffef15801745eb0496676ea17a1a2b10c9e4707
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552638"
---
# <a name="queued-rejected-messages-per-second"></a><span data-ttu-id="21044-102">Zakolejkowane komunikaty odrzucone na sekundę</span><span class="sxs-lookup"><span data-stu-id="21044-102">Queued Rejected Messages Per Second</span></span>
<span data-ttu-id="21044-103">Nazwa licznika: odrzucone wiadomości w kolejce na sekundę.</span><span class="sxs-lookup"><span data-stu-id="21044-103">Counter Name: Queued Messages Rejected Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="21044-104">Opis</span><span class="sxs-lookup"><span data-stu-id="21044-104">Description</span></span>  
 <span data-ttu-id="21044-105">Liczba komunikatów odrzuconych przez transport w kolejce w tej usłudze w drugim.</span><span class="sxs-lookup"><span data-stu-id="21044-105">Number of messages that are rejected by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="21044-106">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="21044-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="21044-107">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="21044-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
