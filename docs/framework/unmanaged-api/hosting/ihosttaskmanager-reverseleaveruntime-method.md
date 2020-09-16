---
title: IHostTaskManager::ReverseLeaveRuntime — Metoda
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseLeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type:
- apiref
ms.openlocfilehash: ea352b189d65e0be6a2bbc81c19a03d1edd8143d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554804"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="6c275-102">IHostTaskManager::ReverseLeaveRuntime — Metoda</span><span class="sxs-lookup"><span data-stu-id="6c275-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="6c275-103">Powiadamia hosta, że kontrola opuszcza środowisko uruchomieniowe języka wspólnego (CLR) i wprowadza niezarządzaną funkcję, która była z kolei wywoływana z kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="6c275-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c275-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6c275-104">Syntax</span></span>  
  
```cpp  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6c275-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="6c275-105">Return Value</span></span>  
  
|<span data-ttu-id="6c275-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c275-106">HRESULT</span></span>|<span data-ttu-id="6c275-107">Opis</span><span class="sxs-lookup"><span data-stu-id="6c275-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c275-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c275-108">S_OK</span></span>|<span data-ttu-id="6c275-109">`ReverseLeaveRuntime` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="6c275-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="6c275-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6c275-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6c275-111">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="6c275-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6c275-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6c275-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6c275-113">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="6c275-113">The call timed out.</span></span>|  
|<span data-ttu-id="6c275-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6c275-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6c275-115">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="6c275-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6c275-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6c275-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6c275-117">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="6c275-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6c275-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6c275-118">E_FAIL</span></span>|<span data-ttu-id="6c275-119">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="6c275-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6c275-120">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="6c275-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6c275-121">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6c275-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6c275-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6c275-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6c275-123">Za mało dostępnej pamięci, aby zakończyć żądaną alokację zasobów.</span><span class="sxs-lookup"><span data-stu-id="6c275-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c275-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6c275-124">Remarks</span></span>  
 <span data-ttu-id="6c275-125">Środowisko CLR wywołuje, `ReverseLeaveRuntime` aby poinformować hosta, że aktualnie wykonywane zadanie zwraca kontrolę do niezarządzanej funkcji, która była z kolei wywoływana z kodu zarządzanego za pośrednictwem wywołania platformy.</span><span class="sxs-lookup"><span data-stu-id="6c275-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="6c275-126">Każde wywołanie `ReverseLeaveRuntime` dopasowuje odpowiednie wywołanie do [ReverseEnterRuntime —](ihosttaskmanager-reverseenterruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="6c275-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c275-127">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6c275-127">Requirements</span></span>  
 <span data-ttu-id="6c275-128">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c275-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c275-129">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6c275-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c275-130">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c275-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c275-131">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c275-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c275-132">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6c275-132">See also</span></span>

- [<span data-ttu-id="6c275-133">CallNeedsHostHook, metoda</span><span class="sxs-lookup"><span data-stu-id="6c275-133">CallNeedsHostHook Method</span></span>](ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="6c275-134">EnterRuntime, metoda</span><span class="sxs-lookup"><span data-stu-id="6c275-134">EnterRuntime Method</span></span>](ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="6c275-135">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6c275-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="6c275-136">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6c275-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="6c275-137">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6c275-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="6c275-138">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6c275-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="6c275-139">LeaveRuntime, metoda</span><span class="sxs-lookup"><span data-stu-id="6c275-139">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)
- <span data-ttu-id="6c275-140">[Bliższe spojrzenie na wywołanie platformy](/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6c275-140">[A Closer Look at Platform Invoke](/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span></span>
