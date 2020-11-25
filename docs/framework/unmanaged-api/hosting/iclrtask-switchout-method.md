---
title: ICLRTask::SwitchOut — Metoda
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
ms.openlocfilehash: 1b27983b3f10eba225442dcd2f5df02062e53ed4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720277"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="d1796-102">ICLRTask::SwitchOut — Metoda</span><span class="sxs-lookup"><span data-stu-id="d1796-102">ICLRTask::SwitchOut Method</span></span>

<span data-ttu-id="d1796-103">Powiadamia środowisko uruchomieniowe języka wspólnego (CLR), że zadanie reprezentowane przez bieżące wystąpienie [ICLRTask](iclrtask-interface.md) nie jest już w stanie obsługiwanym.</span><span class="sxs-lookup"><span data-stu-id="d1796-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1796-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d1796-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d1796-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="d1796-105">Return Value</span></span>  
  
|<span data-ttu-id="d1796-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d1796-106">HRESULT</span></span>|<span data-ttu-id="d1796-107">Opis</span><span class="sxs-lookup"><span data-stu-id="d1796-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d1796-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d1796-108">S_OK</span></span>|<span data-ttu-id="d1796-109">`SwitchOut` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="d1796-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="d1796-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d1796-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d1796-111">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="d1796-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d1796-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d1796-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d1796-113">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="d1796-113">The call timed out.</span></span>|  
|<span data-ttu-id="d1796-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d1796-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d1796-115">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="d1796-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d1796-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d1796-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d1796-117">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="d1796-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d1796-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d1796-118">E_FAIL</span></span>|<span data-ttu-id="d1796-119">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="d1796-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d1796-120">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="d1796-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d1796-121">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d1796-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1796-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d1796-122">Remarks</span></span>  

 <span data-ttu-id="d1796-123">Host wywołuje `SwitchOut` w celu informowania środowiska CLR o tymczasowym zatrzymaniu wykonywania zadania, które `ICLRTask` reprezentuje bieżące wystąpienie, i ponownie planuje zadanie.</span><span class="sxs-lookup"><span data-stu-id="d1796-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1796-124">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d1796-124">Requirements</span></span>  

 <span data-ttu-id="d1796-125">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1796-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1796-126">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d1796-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d1796-127">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d1796-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1796-128">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1796-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1796-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d1796-129">See also</span></span>

- [<span data-ttu-id="d1796-130">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d1796-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="d1796-131">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d1796-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="d1796-132">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d1796-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="d1796-133">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d1796-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
