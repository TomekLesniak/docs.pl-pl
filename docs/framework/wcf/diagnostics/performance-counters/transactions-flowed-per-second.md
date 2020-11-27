---
title: Przepływ transakcji na sekundę
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: b47219bd58a9b6c4401baa73177928ddca5b6a8b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254145"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="fd152-102">Przepływ transakcji na sekundę</span><span class="sxs-lookup"><span data-stu-id="fd152-102">Transactions Flowed Per Second</span></span>

<span data-ttu-id="fd152-103">Nazwa licznika: przepływające transakcje na sekundę</span><span class="sxs-lookup"><span data-stu-id="fd152-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="fd152-104">Opis</span><span class="sxs-lookup"><span data-stu-id="fd152-104">Description</span></span>  

 <span data-ttu-id="fd152-105">Liczba transakcji przepływających do tej operacji w drugim.</span><span class="sxs-lookup"><span data-stu-id="fd152-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="fd152-106">Ten licznik jest zwiększany za każdym razem, gdy w komunikacie wysyłanym do operacji jest obecny identyfikator transakcji.</span><span class="sxs-lookup"><span data-stu-id="fd152-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="fd152-107">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="fd152-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="fd152-108">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="fd152-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
