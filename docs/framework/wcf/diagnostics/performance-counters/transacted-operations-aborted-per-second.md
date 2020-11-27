---
title: Przerwane operacje transakcyjne na sekundę
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: 1a23420ca1521a11168a859eef61cb8861a144f9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250024"
---
# <a name="transacted-operations-aborted-per-second"></a><span data-ttu-id="684b3-102">Przerwane operacje transakcyjne na sekundę</span><span class="sxs-lookup"><span data-stu-id="684b3-102">Transacted Operations Aborted Per Second</span></span>

<span data-ttu-id="684b3-103">Nazwa licznika: przerwane Operacje transakcyjne na sekundę.</span><span class="sxs-lookup"><span data-stu-id="684b3-103">Counter Name: Transacted Operations Aborted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="684b3-104">Opis</span><span class="sxs-lookup"><span data-stu-id="684b3-104">Description</span></span>  

 <span data-ttu-id="684b3-105">Liczba operacji transakcyjnych, które zostały przerwane w tej usłudze w drugim.</span><span class="sxs-lookup"><span data-stu-id="684b3-105">Number of transactional operations that have been aborted in this service in a second.</span></span>  
  
 <span data-ttu-id="684b3-106">Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły.</span><span class="sxs-lookup"><span data-stu-id="684b3-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="684b3-107">(N 1-N 0)/((D 1-D 0)/F)</span><span class="sxs-lookup"><span data-stu-id="684b3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
