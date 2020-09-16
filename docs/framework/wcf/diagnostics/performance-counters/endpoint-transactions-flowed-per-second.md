---
title: 'Punkt końcowy: Przekazane transakcje na sekundę'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 9391651eaaca130ef47ddee9daa95b1f8c116892
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553795"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="1863e-102">Punkt końcowy: Przekazane transakcje na sekundę</span><span class="sxs-lookup"><span data-stu-id="1863e-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="1863e-103">Nazwa licznika: przepływające na sekundę transakcje.</span><span class="sxs-lookup"><span data-stu-id="1863e-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1863e-104">Opis</span><span class="sxs-lookup"><span data-stu-id="1863e-104">Description</span></span>  
 <span data-ttu-id="1863e-105">Liczba transakcji przepływających do operacji w tym punkcie końcowym w drugim.</span><span class="sxs-lookup"><span data-stu-id="1863e-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="1863e-106">Ten licznik jest zwiększany za każdym razem, gdy w komunikacie wysyłanym do punktu końcowego jest obecny identyfikator transakcji.</span><span class="sxs-lookup"><span data-stu-id="1863e-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="1863e-107">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="1863e-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="1863e-108">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="1863e-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
