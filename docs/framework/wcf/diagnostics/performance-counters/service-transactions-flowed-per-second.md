---
title: 'Usługa: przepływające transakcje na sekundę'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: 2ed9f6711c998bbd3f1130b9a91d8ac850821a07
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559327"
---
# <a name="service-transactions-flowed-per-second"></a><span data-ttu-id="38d5b-102">Usługa: przepływające transakcje na sekundę</span><span class="sxs-lookup"><span data-stu-id="38d5b-102">Service: Transactions Flowed Per Second</span></span>
<span data-ttu-id="38d5b-103">Nazwa licznika: przepływające na sekundę transakcje.</span><span class="sxs-lookup"><span data-stu-id="38d5b-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="38d5b-104">Opis</span><span class="sxs-lookup"><span data-stu-id="38d5b-104">Description</span></span>  
 <span data-ttu-id="38d5b-105">Liczba transakcji przepływających do operacji w tej usłudze w drugim.</span><span class="sxs-lookup"><span data-stu-id="38d5b-105">Number of transactions flowed to operations in this service in a second.</span></span>  
  
 <span data-ttu-id="38d5b-106">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="38d5b-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="38d5b-107">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="38d5b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
