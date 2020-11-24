---
title: IHostManualEvent::Set — Metoda
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type:
- apiref
ms.openlocfilehash: bc2b178c6c26a6de62982c35d5aeb9ea5359c2bf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679133"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="3f740-102">IHostManualEvent::Set — Metoda</span><span class="sxs-lookup"><span data-stu-id="3f740-102">IHostManualEvent::Set Method</span></span>

<span data-ttu-id="3f740-103">Ustawia bieżące wystąpienie [IHostManualEvent](ihostmanualevent-interface.md) na sygnał.</span><span class="sxs-lookup"><span data-stu-id="3f740-103">Sets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f740-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3f740-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3f740-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="3f740-105">Return Value</span></span>  
  
|<span data-ttu-id="3f740-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3f740-106">HRESULT</span></span>|<span data-ttu-id="3f740-107">Opis</span><span class="sxs-lookup"><span data-stu-id="3f740-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3f740-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f740-108">S_OK</span></span>|<span data-ttu-id="3f740-109">`Set` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="3f740-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="3f740-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3f740-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3f740-111">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="3f740-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3f740-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3f740-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3f740-113">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="3f740-113">The call timed out.</span></span>|  
|<span data-ttu-id="3f740-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f740-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3f740-115">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="3f740-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3f740-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3f740-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3f740-117">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="3f740-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3f740-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3f740-118">E_FAIL</span></span>|<span data-ttu-id="3f740-119">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="3f740-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3f740-120">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="3f740-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3f740-121">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3f740-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3f740-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3f740-122">Requirements</span></span>  

 <span data-ttu-id="3f740-123">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f740-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f740-124">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3f740-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f740-125">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3f740-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f740-126">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f740-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f740-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3f740-127">See also</span></span>

- [<span data-ttu-id="3f740-128">ICLRSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3f740-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="3f740-129">IHostAutoEvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3f740-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="3f740-130">IHostManualEvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3f740-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="3f740-131">IHostSemaphore — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3f740-131">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="3f740-132">IHostSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3f740-132">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
