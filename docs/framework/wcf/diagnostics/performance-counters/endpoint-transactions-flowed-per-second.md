---
title: 'Punkt końcowy: Przekazane transakcje na sekundę'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: b814d7ca9e286426289c611b3a6bf5a52c1b2335
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256433"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="9ac50-102">Punkt końcowy: Przekazane transakcje na sekundę</span><span class="sxs-lookup"><span data-stu-id="9ac50-102">Endpoint: Transactions Flowed Per Second</span></span>

<span data-ttu-id="9ac50-103">Nazwa licznika: przepływające na sekundę transakcje.</span><span class="sxs-lookup"><span data-stu-id="9ac50-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9ac50-104">Opis</span><span class="sxs-lookup"><span data-stu-id="9ac50-104">Description</span></span>  

 <span data-ttu-id="9ac50-105">Liczba transakcji przepływających do operacji w tym punkcie końcowym w drugim.</span><span class="sxs-lookup"><span data-stu-id="9ac50-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="9ac50-106">Ten licznik jest zwiększany za każdym razem, gdy w komunikacie wysyłanym do punktu końcowego jest obecny identyfikator transakcji.</span><span class="sxs-lookup"><span data-stu-id="9ac50-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="9ac50-107">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="9ac50-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="9ac50-108">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="9ac50-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
