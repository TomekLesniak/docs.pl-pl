---
title: IHostTask — Interfejs
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
ms.openlocfilehash: 10efe853c9a7ad7676058bc01b07063c557623d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699225"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="e1e7b-102">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e1e7b-102">IHostTask Interface</span></span>

<span data-ttu-id="e1e7b-103">Dostarcza metody, które umożliwiają środowisko uruchomieniowe języka wspólnego (CLR) komunikowanie się z hostem w celu zarządzania zadaniami.</span><span class="sxs-lookup"><span data-stu-id="e1e7b-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1e7b-104">Metody</span><span class="sxs-lookup"><span data-stu-id="e1e7b-104">Methods</span></span>  
  
|<span data-ttu-id="e1e7b-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="e1e7b-105">Method</span></span>|<span data-ttu-id="e1e7b-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e1e7b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1e7b-107">Alert, metoda</span><span class="sxs-lookup"><span data-stu-id="e1e7b-107">Alert Method</span></span>](ihosttask-alert-method.md)|<span data-ttu-id="e1e7b-108">Żąda, aby Host wznowił zadanie reprezentowane przez bieżące `IHostTask` wystąpienie, więc zadanie można przerwać.</span><span class="sxs-lookup"><span data-stu-id="e1e7b-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="e1e7b-109">GetPriority, metoda</span><span class="sxs-lookup"><span data-stu-id="e1e7b-109">GetPriority Method</span></span>](ihosttask-getpriority-method.md)|<span data-ttu-id="e1e7b-110">Pobiera poziom priorytetu wątku zadania reprezentowanego przez bieżące `IHostTask` wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="e1e7b-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="e1e7b-111">Join, metoda</span><span class="sxs-lookup"><span data-stu-id="e1e7b-111">Join Method</span></span>](ihosttask-join-method.md)|<span data-ttu-id="e1e7b-112">Blokuje zadanie wywołujące do momentu zakończenia zadania reprezentowanego przez bieżące `IHostTask` wystąpienie, upłynie określony przedział czasu lub [IHostTask:: Alert](ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e1e7b-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="e1e7b-113">SetCLRTask, metoda</span><span class="sxs-lookup"><span data-stu-id="e1e7b-113">SetCLRTask Method</span></span>](ihosttask-setclrtask-method.md)|<span data-ttu-id="e1e7b-114">Kojarzy wystąpienie [interfejsu ICLRTask](iclrtask-interface.md) z bieżącym `IHostTask` wystąpieniem.</span><span class="sxs-lookup"><span data-stu-id="e1e7b-114">Associates an [ICLRTask Interface](iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="e1e7b-115">SetPriority, metoda</span><span class="sxs-lookup"><span data-stu-id="e1e7b-115">SetPriority Method</span></span>](ihosttask-setpriority-method.md)|<span data-ttu-id="e1e7b-116">Żądania, za pomocą których Host dostosowuje poziom priorytetu wątku dla zadania reprezentowanego przez bieżące `IHostTask` wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="e1e7b-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="e1e7b-117">Start — Metoda</span><span class="sxs-lookup"><span data-stu-id="e1e7b-117">Start Method</span></span>](ihosttask-start-method.md)|<span data-ttu-id="e1e7b-118">Żąda, aby Host przeniesieł zadanie reprezentowane przez bieżące `IHostTask` wystąpienie ze stanu wstrzymania do stanu na żywo, w którym można wykonać kod.</span><span class="sxs-lookup"><span data-stu-id="e1e7b-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1e7b-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e1e7b-119">Remarks</span></span>  

 <span data-ttu-id="e1e7b-120">Środowisko CLR wywołuje metody zdefiniowane przez, `IHostTask` Aby uruchomić zadanie, ustawić jego poziom priorytetu wątku i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="e1e7b-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1e7b-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e1e7b-121">Requirements</span></span>  

 <span data-ttu-id="e1e7b-122">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1e7b-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1e7b-123">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e1e7b-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1e7b-124">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e1e7b-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1e7b-125">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1e7b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e7b-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e1e7b-126">See also</span></span>

- [<span data-ttu-id="e1e7b-127">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e1e7b-127">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="e1e7b-128">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e1e7b-128">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="e1e7b-129">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e1e7b-129">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="e1e7b-130">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="e1e7b-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
