---
title: IHostTask::Alert — Metoda
ms.date: 03/30/2017
api_name:
- IHostTask.Alert
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Alert
helpviewer_keywords:
- IHostTask::Alert method [.NET Framework hosting]
- Alert method, IHostTask interface [.NET Framework hosting]
ms.assetid: 5245d4b5-b6c3-48df-9cb9-8caf059f43fb
topic_type:
- apiref
ms.openlocfilehash: 5a4870a4472081a78cd1fade51f441c22aa5eb48
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720480"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="0f6ba-102">IHostTask::Alert — Metoda</span><span class="sxs-lookup"><span data-stu-id="0f6ba-102">IHostTask::Alert Method</span></span>

<span data-ttu-id="0f6ba-103">Żąda, aby Host wznowił zadanie reprezentowane przez bieżące wystąpienie [IHostTask](ihosttask-interface.md) , więc zadanie można przerwać.</span><span class="sxs-lookup"><span data-stu-id="0f6ba-103">Requests that the host wake the task represented by the current [IHostTask](ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f6ba-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0f6ba-104">Syntax</span></span>  
  
```cpp  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0f6ba-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="0f6ba-105">Return Value</span></span>  
  
|<span data-ttu-id="0f6ba-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f6ba-106">HRESULT</span></span>|<span data-ttu-id="0f6ba-107">Opis</span><span class="sxs-lookup"><span data-stu-id="0f6ba-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f6ba-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f6ba-108">S_OK</span></span>|<span data-ttu-id="0f6ba-109">Metoda została pomyślnie zwrócona.</span><span class="sxs-lookup"><span data-stu-id="0f6ba-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="0f6ba-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0f6ba-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f6ba-111">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="0f6ba-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f6ba-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f6ba-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f6ba-113">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="0f6ba-113">The call timed out.</span></span>|  
|<span data-ttu-id="0f6ba-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f6ba-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f6ba-115">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="0f6ba-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f6ba-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f6ba-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f6ba-117">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="0f6ba-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f6ba-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f6ba-118">E_FAIL</span></span>|<span data-ttu-id="0f6ba-119">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="0f6ba-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f6ba-120">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="0f6ba-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0f6ba-121">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0f6ba-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f6ba-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0f6ba-122">Remarks</span></span>  

 <span data-ttu-id="0f6ba-123">Środowisko CLR wywołuje `Alert` metodę, gdy <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> jest wywoływana z kodu użytkownika lub gdy jest <xref:System.AppDomain> skojarzony z bieżącym <xref:System.Threading.Thread> zamknięciem.</span><span class="sxs-lookup"><span data-stu-id="0f6ba-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="0f6ba-124">Host musi zwrócić natychmiast, ponieważ wywołanie zostało wykonane asynchronicznie.</span><span class="sxs-lookup"><span data-stu-id="0f6ba-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="0f6ba-125">Jeśli host nie może natychmiast ostrzec zadania, musi wznowić działanie przy następnym wejściu w stan, w którym można otrzymywać alerty.</span><span class="sxs-lookup"><span data-stu-id="0f6ba-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f6ba-126">`Alert` ma wpływ tylko na te zadania, do których środowisko uruchomieniowe przekazało [WAIT_OPTION](wait-option-enumeration.md) wartość WAIT_ALERTABLE do metod takich jak [Join](ihosttask-join-method.md).</span><span class="sxs-lookup"><span data-stu-id="0f6ba-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f6ba-127">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0f6ba-127">Requirements</span></span>  

 <span data-ttu-id="0f6ba-128">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f6ba-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f6ba-129">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0f6ba-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f6ba-130">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f6ba-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f6ba-131">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f6ba-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f6ba-132">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0f6ba-132">See also</span></span>

- [<span data-ttu-id="0f6ba-133">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0f6ba-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="0f6ba-134">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0f6ba-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="0f6ba-135">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0f6ba-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="0f6ba-136">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0f6ba-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
