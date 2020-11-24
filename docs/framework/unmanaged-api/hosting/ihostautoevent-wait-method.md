---
title: IHostAutoEvent::Wait — Metoda
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type:
- apiref
ms.openlocfilehash: f07958a1a21bb3e93e4ca8202a65407b39188af4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680784"
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="e1f7b-102">IHostAutoEvent::Wait — Metoda</span><span class="sxs-lookup"><span data-stu-id="e1f7b-102">IHostAutoEvent::Wait Method</span></span>

<span data-ttu-id="e1f7b-103">Powoduje, że bieżące wystąpienie [IHostAutoEvent](ihostautoevent-interface.md) zaczeka, aż jego właścicielem lub upłynie określony czas.</span><span class="sxs-lookup"><span data-stu-id="e1f7b-103">Causes the current [IHostAutoEvent](ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1f7b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e1f7b-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1f7b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e1f7b-105">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="e1f7b-106">podczas Liczba milisekund, przez jaką bieżące `IHostAutoEvent` wystąpienie powinno czekać przed zwróceniem, jeśli żaden wątek ani włókna nie przejmują własności.</span><span class="sxs-lookup"><span data-stu-id="e1f7b-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="e1f7b-107">podczas Jedną z wartości [WAIT_OPTION](wait-option-enumeration.md) , określając akcję, którą powinien wykonać host, jeśli ta operacja jest blokowana.</span><span class="sxs-lookup"><span data-stu-id="e1f7b-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1f7b-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="e1f7b-108">Return Value</span></span>  
  
|<span data-ttu-id="e1f7b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1f7b-109">HRESULT</span></span>|<span data-ttu-id="e1f7b-110">Opis</span><span class="sxs-lookup"><span data-stu-id="e1f7b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1f7b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1f7b-111">S_OK</span></span>|<span data-ttu-id="e1f7b-112">`Wait` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="e1f7b-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="e1f7b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e1f7b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e1f7b-114">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="e1f7b-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e1f7b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e1f7b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e1f7b-116">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="e1f7b-116">The call timed out.</span></span>|  
|<span data-ttu-id="e1f7b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1f7b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e1f7b-118">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="e1f7b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e1f7b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e1f7b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e1f7b-120">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="e1f7b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e1f7b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e1f7b-121">E_FAIL</span></span>|<span data-ttu-id="e1f7b-122">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="e1f7b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e1f7b-123">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="e1f7b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e1f7b-124">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e1f7b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e1f7b-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="e1f7b-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="e1f7b-126">Host wykrył zakleszczenie w interwale oczekiwania i wybiera zdarzenie reprezentowane przez bieżące `IHostAutoEvent` wystąpienie jako ofiarę zakleszczenia.</span><span class="sxs-lookup"><span data-stu-id="e1f7b-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1f7b-127">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e1f7b-127">Requirements</span></span>  

 <span data-ttu-id="e1f7b-128">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1f7b-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1f7b-129">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e1f7b-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1f7b-130">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e1f7b-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1f7b-131">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1f7b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1f7b-132">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e1f7b-132">See also</span></span>

- [<span data-ttu-id="e1f7b-133">ICLRSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e1f7b-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="e1f7b-134">IHostAutoEvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e1f7b-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="e1f7b-135">IHostManualEvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e1f7b-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="e1f7b-136">IHostSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e1f7b-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
