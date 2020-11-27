---
title: Zatwierdzone operacje transakcyjne na sekundę
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: deb29820aab09adad8825a299145772892117948
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250011"
---
# <a name="transacted-operations-committed-per-second"></a><span data-ttu-id="8b070-102">Zatwierdzone operacje transakcyjne na sekundę</span><span class="sxs-lookup"><span data-stu-id="8b070-102">Transacted Operations Committed Per Second</span></span>

<span data-ttu-id="8b070-103">Nazwa licznika: zatwierdzone Operacje transakcyjne na sekundę.</span><span class="sxs-lookup"><span data-stu-id="8b070-103">Counter Name: Transacted Operations Committed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8b070-104">Opis</span><span class="sxs-lookup"><span data-stu-id="8b070-104">Description</span></span>  

 <span data-ttu-id="8b070-105">Liczba operacji transakcyjnych, które zostały zatwierdzone w tej usłudze w drugim.</span><span class="sxs-lookup"><span data-stu-id="8b070-105">Number of transactional operations that have been committed in this service in a second.</span></span>  
  
 <span data-ttu-id="8b070-106">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="8b070-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="8b070-107">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="8b070-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
