---
title: IHostGCManager::SuspensionStarting — Metoda
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
ms.openlocfilehash: 7e610676e86dde3ab0bdea2ce2314f02b3da9976
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729502"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="2cf5e-102">IHostGCManager::SuspensionStarting — Metoda</span><span class="sxs-lookup"><span data-stu-id="2cf5e-102">IHostGCManager::SuspensionStarting Method</span></span>

<span data-ttu-id="2cf5e-103">Powiadamia hosta, że środowisko uruchomieniowe języka wspólnego (CLR) wstrzymuje wykonywanie zadań, aby wykonać wyrzucanie elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="2cf5e-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cf5e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2cf5e-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2cf5e-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="2cf5e-105">Return Value</span></span>  
  
|<span data-ttu-id="2cf5e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2cf5e-106">HRESULT</span></span>|<span data-ttu-id="2cf5e-107">Opis</span><span class="sxs-lookup"><span data-stu-id="2cf5e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2cf5e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2cf5e-108">S_OK</span></span>|<span data-ttu-id="2cf5e-109">`SuspensionStarting` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="2cf5e-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="2cf5e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2cf5e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2cf5e-111">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="2cf5e-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2cf5e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2cf5e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2cf5e-113">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="2cf5e-113">The call timed out.</span></span>|  
|<span data-ttu-id="2cf5e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2cf5e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2cf5e-115">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="2cf5e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2cf5e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2cf5e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2cf5e-117">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="2cf5e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2cf5e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2cf5e-118">E_FAIL</span></span>|<span data-ttu-id="2cf5e-119">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="2cf5e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2cf5e-120">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="2cf5e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2cf5e-121">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2cf5e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cf5e-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2cf5e-122">Remarks</span></span>  

 <span data-ttu-id="2cf5e-123">Środowisko CLR wywołuje, `SuspensionStarting` aby poinformować hosta, że występuje wyrzucanie elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="2cf5e-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2cf5e-124">Nie należy ponownie zaplanować tego zadania.</span><span class="sxs-lookup"><span data-stu-id="2cf5e-124">Do not reschedule this task.</span></span> <span data-ttu-id="2cf5e-125">Host musi ponownie zaplanować zadanie, gdy zostanie wywołane [ThreadIsBlockingForSuspension —](ihostgcmanager-threadisblockingforsuspension-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2cf5e-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cf5e-126">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2cf5e-126">Requirements</span></span>  

 <span data-ttu-id="2cf5e-127">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cf5e-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cf5e-128">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2cf5e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2cf5e-129">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2cf5e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2cf5e-130">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cf5e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cf5e-131">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2cf5e-131">See also</span></span>

- [<span data-ttu-id="2cf5e-132">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2cf5e-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="2cf5e-133">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2cf5e-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="2cf5e-134">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2cf5e-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="2cf5e-135">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2cf5e-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="2cf5e-136">IHostGCManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2cf5e-136">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
