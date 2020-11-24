---
title: IHostManualEvent::Reset — Metoda
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Reset
helpviewer_keywords:
- Reset method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Reset method [.NET Framework hosting]
ms.assetid: 0d101168-b5e3-49ce-90c7-85cf2db83c4c
topic_type:
- apiref
ms.openlocfilehash: 5653f874ef7a681f6667b3508b82ac493234cc4e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673153"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="19d5e-102">IHostManualEvent::Reset — Metoda</span><span class="sxs-lookup"><span data-stu-id="19d5e-102">IHostManualEvent::Reset Method</span></span>

<span data-ttu-id="19d5e-103">Resetuje bieżące wystąpienie [IHostManualEvent](ihostmanualevent-interface.md) do stanu niesygnalizującego.</span><span class="sxs-lookup"><span data-stu-id="19d5e-103">Resets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19d5e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="19d5e-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="19d5e-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="19d5e-105">Return Value</span></span>  
  
|<span data-ttu-id="19d5e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19d5e-106">HRESULT</span></span>|<span data-ttu-id="19d5e-107">Opis</span><span class="sxs-lookup"><span data-stu-id="19d5e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19d5e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="19d5e-108">S_OK</span></span>|<span data-ttu-id="19d5e-109">`Reset` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="19d5e-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="19d5e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="19d5e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="19d5e-111">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="19d5e-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="19d5e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="19d5e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="19d5e-113">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="19d5e-113">The call timed out.</span></span>|  
|<span data-ttu-id="19d5e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="19d5e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="19d5e-115">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="19d5e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="19d5e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="19d5e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="19d5e-117">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="19d5e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="19d5e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="19d5e-118">E_FAIL</span></span>|<span data-ttu-id="19d5e-119">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="19d5e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="19d5e-120">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="19d5e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="19d5e-121">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="19d5e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="19d5e-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="19d5e-122">Requirements</span></span>  

 <span data-ttu-id="19d5e-123">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19d5e-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19d5e-124">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="19d5e-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19d5e-125">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19d5e-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19d5e-126">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19d5e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19d5e-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="19d5e-127">See also</span></span>

- [<span data-ttu-id="19d5e-128">ICLRSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="19d5e-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="19d5e-129">IHostAutoEvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="19d5e-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="19d5e-130">IHostManualEvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="19d5e-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="19d5e-131">IHostSemaphore — Interfejs</span><span class="sxs-lookup"><span data-stu-id="19d5e-131">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="19d5e-132">IHostSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="19d5e-132">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
