---
title: IHostManualEvent — Interfejs
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 50e37b770e3ee6e0a5cdfca61fc5b09749e5735f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673206"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="e9c1e-102">IHostManualEvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e9c1e-102">IHostManualEvent Interface</span></span>

<span data-ttu-id="e9c1e-103">Zapewnia implementację hosta reprezentacji zdarzenia resetowania ręcznego.</span><span class="sxs-lookup"><span data-stu-id="e9c1e-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9c1e-104">Metody</span><span class="sxs-lookup"><span data-stu-id="e9c1e-104">Methods</span></span>  
  
|<span data-ttu-id="e9c1e-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="e9c1e-105">Method</span></span>|<span data-ttu-id="e9c1e-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e9c1e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9c1e-107">Reset — Metoda</span><span class="sxs-lookup"><span data-stu-id="e9c1e-107">Reset Method</span></span>](ihostmanualevent-reset-method.md)|<span data-ttu-id="e9c1e-108">Resetuje bieżące `IHostManualEvent` wystąpienie do stanu niesygnalizującego.</span><span class="sxs-lookup"><span data-stu-id="e9c1e-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="e9c1e-109">Set, metoda</span><span class="sxs-lookup"><span data-stu-id="e9c1e-109">Set Method</span></span>](ihostmanualevent-set-method.md)|<span data-ttu-id="e9c1e-110">Ustawia bieżące `IHostManualEvent` wystąpienie na sygnał.</span><span class="sxs-lookup"><span data-stu-id="e9c1e-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="e9c1e-111">Wait — Metoda</span><span class="sxs-lookup"><span data-stu-id="e9c1e-111">Wait Method</span></span>](ihostmanualevent-wait-method.md)|<span data-ttu-id="e9c1e-112">Powoduje, że bieżące `IHostManualEvent` wystąpienie zaczeka, aż będzie jego właścicielem lub upłynie określony czas.</span><span class="sxs-lookup"><span data-stu-id="e9c1e-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9c1e-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e9c1e-113">Requirements</span></span>  

 <span data-ttu-id="e9c1e-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9c1e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9c1e-115">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e9c1e-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9c1e-116">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9c1e-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9c1e-117">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9c1e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c1e-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e9c1e-118">See also</span></span>

- [<span data-ttu-id="e9c1e-119">ICLRSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e9c1e-119">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="e9c1e-120">IHostAutoEvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e9c1e-120">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="e9c1e-121">IHostSemaphore — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e9c1e-121">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="e9c1e-122">IHostSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e9c1e-122">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="e9c1e-123">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="e9c1e-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
