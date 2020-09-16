---
title: Zakolejkowane komunikaty porzucone na sekundę
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: 22b6091693b6a4c8eac9816e8ac15660f4636ec9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552755"
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="b38e4-102">Zakolejkowane komunikaty porzucone na sekundę</span><span class="sxs-lookup"><span data-stu-id="b38e4-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="b38e4-103">Nazwa licznika: liczba porzuconych komunikatów w kolejce na sekundę.</span><span class="sxs-lookup"><span data-stu-id="b38e4-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b38e4-104">Opis</span><span class="sxs-lookup"><span data-stu-id="b38e4-104">Description</span></span>  
 <span data-ttu-id="b38e4-105">Liczba komunikatów porzuconych przez transport w kolejce w tej usłudze w drugim.</span><span class="sxs-lookup"><span data-stu-id="b38e4-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="b38e4-106">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="b38e4-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b38e4-107">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="b38e4-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
