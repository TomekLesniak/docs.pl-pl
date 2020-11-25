---
title: IHostCrst::SetSpinCount — Metoda
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
ms.openlocfilehash: 22274759f931da614a234efe0a6f6eb3aade027c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729567"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="4e4c0-102">IHostCrst::SetSpinCount — Metoda</span><span class="sxs-lookup"><span data-stu-id="4e4c0-102">IHostCrst::SetSpinCount Method</span></span>

<span data-ttu-id="4e4c0-103">Ustawia liczbę obrotów dla bieżącego wystąpienia [IHostCrst](ihostcrst-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4e4c0-103">Sets the spin count for the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e4c0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4e4c0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e4c0-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="4e4c0-105">Parameters</span></span>  

 `dwSpinCount`  
 <span data-ttu-id="4e4c0-106">podczas Nowa liczba obrotów dla bieżącego `IHostCrst` wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="4e4c0-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e4c0-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="4e4c0-107">Return Value</span></span>  
  
|<span data-ttu-id="4e4c0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e4c0-108">HRESULT</span></span>|<span data-ttu-id="4e4c0-109">Opis</span><span class="sxs-lookup"><span data-stu-id="4e4c0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e4c0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e4c0-110">S_OK</span></span>|<span data-ttu-id="4e4c0-111">`SetSpinCount` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="4e4c0-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="4e4c0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4e4c0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4e4c0-113">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="4e4c0-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4e4c0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4e4c0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4e4c0-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="4e4c0-115">The call timed out.</span></span>|  
|<span data-ttu-id="4e4c0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4e4c0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4e4c0-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="4e4c0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4e4c0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4e4c0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4e4c0-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="4e4c0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4e4c0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4e4c0-120">E_FAIL</span></span>|<span data-ttu-id="4e4c0-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="4e4c0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4e4c0-122">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="4e4c0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4e4c0-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4e4c0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e4c0-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4e4c0-124">Remarks</span></span>  

 <span data-ttu-id="4e4c0-125">W przypadku systemów wieloprocesorowych, jeśli Sekcja krytyczna reprezentowana przez bieżące `IHostCrst` wystąpienie jest niedostępna, wywołujący wątek zostanie `dwSpinCount` opóźniony przed wywołaniem [IHostSemaphore:: Poczekaj](ihostsemaphore-wait-method.md) na semafor skojarzony z sekcją krytyczną.</span><span class="sxs-lookup"><span data-stu-id="4e4c0-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="4e4c0-126">Jeśli Sekcja krytyczna zostanie zwolniona podczas operacji pokrętła, wątek wywołujący unika operacji oczekiwania.</span><span class="sxs-lookup"><span data-stu-id="4e4c0-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="4e4c0-127">Użycie `dwSpinCount` jest identyczne z użyciem parametru o tej samej nazwie w `InitializeCriticalSectionAndSpinCount` funkcji Win32.</span><span class="sxs-lookup"><span data-stu-id="4e4c0-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e4c0-128">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4e4c0-128">Requirements</span></span>  

 <span data-ttu-id="4e4c0-129">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e4c0-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e4c0-130">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4e4c0-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e4c0-131">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e4c0-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e4c0-132">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e4c0-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e4c0-133">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4e4c0-133">See also</span></span>

- [<span data-ttu-id="4e4c0-134">ICLRSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4e4c0-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="4e4c0-135">IHostCrst — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4e4c0-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="4e4c0-136">IHostSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4e4c0-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
