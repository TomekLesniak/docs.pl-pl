---
title: IHostCrst::Leave — Metoda
ms.date: 03/30/2017
api_name:
- IHostCrst.Leave
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type:
- apiref
ms.openlocfilehash: 0752afb42b8c512450b047a5e2e7e1ff34533487
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729580"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="4cf02-102">IHostCrst::Leave — Metoda</span><span class="sxs-lookup"><span data-stu-id="4cf02-102">IHostCrst::Leave Method</span></span>

<span data-ttu-id="4cf02-103">Pozostawia sekcję krytyczną, która jest reprezentowana przez bieżące wystąpienie elementu [IHostCrst](ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="4cf02-103">Leaves the critical section that is represented by the current instance of [IHostCrst](ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cf02-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4cf02-104">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4cf02-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="4cf02-105">Return Value</span></span>  
  
|<span data-ttu-id="4cf02-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4cf02-106">HRESULT</span></span>|<span data-ttu-id="4cf02-107">Opis</span><span class="sxs-lookup"><span data-stu-id="4cf02-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4cf02-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="4cf02-108">S_OK</span></span>|<span data-ttu-id="4cf02-109">`Leave` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="4cf02-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="4cf02-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4cf02-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4cf02-111">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="4cf02-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4cf02-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4cf02-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4cf02-113">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="4cf02-113">The call timed out.</span></span>|  
|<span data-ttu-id="4cf02-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4cf02-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4cf02-115">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="4cf02-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4cf02-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4cf02-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4cf02-117">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="4cf02-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4cf02-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4cf02-118">E_FAIL</span></span>|<span data-ttu-id="4cf02-119">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="4cf02-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4cf02-120">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="4cf02-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4cf02-121">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4cf02-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cf02-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4cf02-122">Remarks</span></span>  

 <span data-ttu-id="4cf02-123">`Leave` zezwala, aby środowisko CLR komunikować się bezpośrednio z implementacją wątkowości hosta, a nie przy użyciu odpowiedniej `LeaveCriticalSection` funkcji Win32.</span><span class="sxs-lookup"><span data-stu-id="4cf02-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="4cf02-124">Wątek, który przejmuje własność sekcji krytycznej reprezentowanej przez bieżące `IHostCrst` wystąpienie, musi wywołać `Leave` raz za każdym razem, gdy wprowadza tę sekcję krytyczną.</span><span class="sxs-lookup"><span data-stu-id="4cf02-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cf02-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4cf02-125">Requirements</span></span>  

 <span data-ttu-id="4cf02-126">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cf02-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cf02-127">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4cf02-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cf02-128">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4cf02-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cf02-129">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cf02-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf02-130">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4cf02-130">See also</span></span>

- [<span data-ttu-id="4cf02-131">ICLRSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4cf02-131">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="4cf02-132">IHostCrst — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4cf02-132">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="4cf02-133">IHostSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4cf02-133">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
