---
title: IHostControl::GetHostManager — Metoda
ms.date: 03/30/2017
api_name:
- IHostControl.GetHostManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type:
- apiref
ms.openlocfilehash: e340dcb5dc093f965e6c08a24a3d65ed0aa6e07a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680835"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="fd9f2-102">IHostControl::GetHostManager — Metoda</span><span class="sxs-lookup"><span data-stu-id="fd9f2-102">IHostControl::GetHostManager Method</span></span>

<span data-ttu-id="fd9f2-103">Pobiera wskaźnik interfejsu do implementacji hosta interfejsu z określonym `IID` .</span><span class="sxs-lookup"><span data-stu-id="fd9f2-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd9f2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fd9f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd9f2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="fd9f2-105">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="fd9f2-106">podczas `IID` Interfejs, który jest wysyłany przez środowisko uruchomieniowe języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="fd9f2-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="fd9f2-107">określoną Wskaźnik do interfejsu zaimplementowanego przez hosta lub wartość null, Jeśli host nie obsługuje tego interfejsu.</span><span class="sxs-lookup"><span data-stu-id="fd9f2-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd9f2-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="fd9f2-108">Return Value</span></span>  
  
|<span data-ttu-id="fd9f2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd9f2-109">HRESULT</span></span>|<span data-ttu-id="fd9f2-110">Opis</span><span class="sxs-lookup"><span data-stu-id="fd9f2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd9f2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd9f2-111">S_OK</span></span>|<span data-ttu-id="fd9f2-112">`GetHostManager` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="fd9f2-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="fd9f2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fd9f2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fd9f2-114">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="fd9f2-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fd9f2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fd9f2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fd9f2-116">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="fd9f2-116">The call timed out.</span></span>|  
|<span data-ttu-id="fd9f2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fd9f2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fd9f2-118">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="fd9f2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fd9f2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fd9f2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fd9f2-120">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="fd9f2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fd9f2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd9f2-121">E_FAIL</span></span>|<span data-ttu-id="fd9f2-122">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="fd9f2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fd9f2-123">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="fd9f2-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fd9f2-124">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fd9f2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fd9f2-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fd9f2-125">E_INVALIDARG</span></span>|<span data-ttu-id="fd9f2-126">Żądana `IID` jest nieprawidłowa.</span><span class="sxs-lookup"><span data-stu-id="fd9f2-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="fd9f2-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="fd9f2-127">E_NOINTERFACE</span></span>|<span data-ttu-id="fd9f2-128">Żądany interfejs nie jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="fd9f2-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd9f2-129">Uwagi</span><span class="sxs-lookup"><span data-stu-id="fd9f2-129">Remarks</span></span>  

 <span data-ttu-id="fd9f2-130">Środowisko CLR wysyła zapytanie do hosta, aby określić, czy obsługuje jeden lub więcej z następujących interfejsów:</span><span class="sxs-lookup"><span data-stu-id="fd9f2-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="fd9f2-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="fd9f2-131">IHostMemoryManager</span></span>](ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="fd9f2-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="fd9f2-132">IHostTaskManager</span></span>](ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="fd9f2-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="fd9f2-133">IHostThreadPoolManager</span></span>](ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="fd9f2-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="fd9f2-134">IHostIoCompletionManager</span></span>](ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="fd9f2-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="fd9f2-135">IHostSyncManager</span></span>](ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="fd9f2-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="fd9f2-136">IHostAssemblyManager</span></span>](ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="fd9f2-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="fd9f2-137">IHostGCManager</span></span>](ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="fd9f2-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="fd9f2-138">IHostPolicyManager</span></span>](ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="fd9f2-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="fd9f2-139">IHostSecurityManager</span></span>](ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="fd9f2-140">Jeśli host obsługuje określony interfejs, ustawia on `ppObject` jego implementację.</span><span class="sxs-lookup"><span data-stu-id="fd9f2-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="fd9f2-141">W przeciwnym razie ustawia `ppObject` wartość null.</span><span class="sxs-lookup"><span data-stu-id="fd9f2-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="fd9f2-142">Środowisko CLR nie wywołuje `Release` menedżerów hostów nawet po jego zamknięciu.</span><span class="sxs-lookup"><span data-stu-id="fd9f2-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd9f2-143">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fd9f2-143">Requirements</span></span>  

 <span data-ttu-id="fd9f2-144">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd9f2-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd9f2-145">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fd9f2-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd9f2-146">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd9f2-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd9f2-147">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd9f2-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd9f2-148">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fd9f2-148">See also</span></span>

- [<span data-ttu-id="fd9f2-149">IHostControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fd9f2-149">IHostControl Interface</span></span>](ihostcontrol-interface.md)
