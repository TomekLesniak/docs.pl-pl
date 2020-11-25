---
title: IHostManualEvent::Wait — Metoda
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
ms.openlocfilehash: 3fe8434ba4a7fc49b99bdf3084ce4f3981f25a9b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719830"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="e36e0-102">IHostManualEvent::Wait — Metoda</span><span class="sxs-lookup"><span data-stu-id="e36e0-102">IHostManualEvent::Wait Method</span></span>

<span data-ttu-id="e36e0-103">Powoduje, że bieżące wystąpienie [IHostManualEvent](ihostmanualevent-interface.md) zaczeka, aż jego właścicielem lub upłynie określony czas.</span><span class="sxs-lookup"><span data-stu-id="e36e0-103">Causes the current [IHostManualEvent](ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e36e0-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e36e0-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e36e0-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e36e0-105">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="e36e0-106">podczas Liczba milisekund oczekiwania przed zwróceniem, jeśli bieżące `IHostManualEvent` wystąpienie nie jest własnością.</span><span class="sxs-lookup"><span data-stu-id="e36e0-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="e36e0-107">podczas Jedna z wartości [WAIT_OPTION](wait-option-enumeration.md) , wskazująca na akcję, którą powinien wykonać host w przypadku tej operacji.</span><span class="sxs-lookup"><span data-stu-id="e36e0-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e36e0-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="e36e0-108">Return Value</span></span>  
  
|<span data-ttu-id="e36e0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e36e0-109">HRESULT</span></span>|<span data-ttu-id="e36e0-110">Opis</span><span class="sxs-lookup"><span data-stu-id="e36e0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e36e0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e36e0-111">S_OK</span></span>|<span data-ttu-id="e36e0-112">`Wait` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="e36e0-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="e36e0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e36e0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e36e0-114">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="e36e0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e36e0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e36e0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e36e0-116">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="e36e0-116">The call timed out.</span></span>|  
|<span data-ttu-id="e36e0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e36e0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e36e0-118">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="e36e0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e36e0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e36e0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e36e0-120">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="e36e0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e36e0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e36e0-121">E_FAIL</span></span>|<span data-ttu-id="e36e0-122">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="e36e0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e36e0-123">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="e36e0-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e36e0-124">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e36e0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e36e0-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="e36e0-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="e36e0-126">Host wykrył zakleszczenie w interwale oczekiwania i wybiera bieżące `IHostManualEvent` wystąpienie jako ofiarę zakleszczenia.</span><span class="sxs-lookup"><span data-stu-id="e36e0-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e36e0-127">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e36e0-127">Requirements</span></span>  

 <span data-ttu-id="e36e0-128">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e36e0-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e36e0-129">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e36e0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e36e0-130">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e36e0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e36e0-131">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e36e0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e36e0-132">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e36e0-132">See also</span></span>

- [<span data-ttu-id="e36e0-133">ICLRSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e36e0-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="e36e0-134">IHostAutoEvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e36e0-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="e36e0-135">IHostManualEvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e36e0-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="e36e0-136">IHostSemaphore — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e36e0-136">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="e36e0-137">IHostSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e36e0-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
