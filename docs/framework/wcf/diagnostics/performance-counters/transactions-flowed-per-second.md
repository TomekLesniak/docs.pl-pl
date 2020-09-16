---
title: Przepływ transakcji na sekundę
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: d55856a5d820df2c668863a2a3e853995a113143
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552209"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="217f7-102">Przepływ transakcji na sekundę</span><span class="sxs-lookup"><span data-stu-id="217f7-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="217f7-103">Nazwa licznika: przepływające transakcje na sekundę</span><span class="sxs-lookup"><span data-stu-id="217f7-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="217f7-104">Opis</span><span class="sxs-lookup"><span data-stu-id="217f7-104">Description</span></span>  
 <span data-ttu-id="217f7-105">Liczba transakcji przepływających do tej operacji w drugim.</span><span class="sxs-lookup"><span data-stu-id="217f7-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="217f7-106">Ten licznik jest zwiększany za każdym razem, gdy w komunikacie wysyłanym do operacji jest obecny identyfikator transakcji.</span><span class="sxs-lookup"><span data-stu-id="217f7-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="217f7-107">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="217f7-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="217f7-108">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="217f7-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
