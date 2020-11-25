---
title: IHostIoCompletionManager::SetCLRIoCompletionManager — Metoda
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetCLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type:
- apiref
ms.openlocfilehash: d370cc81942269bd79e06e0fa57fe5d79832b3c2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724848"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="dcd60-102">IHostIoCompletionManager::SetCLRIoCompletionManager — Metoda</span><span class="sxs-lookup"><span data-stu-id="dcd60-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>

<span data-ttu-id="dcd60-103">Dostarcza host ze wskaźnikiem interfejsu do wystąpienia [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) zaimplementowanego przez środowisko uruchomieniowe języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="dcd60-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcd60-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="dcd60-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcd60-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="dcd60-105">Parameters</span></span>  

 `pManager`  
 <span data-ttu-id="dcd60-106">podczas Wskaźnik interfejsu do `ICLRIoCompletionManager` wystąpienia dostarczonego przez środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="dcd60-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dcd60-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="dcd60-107">Return Value</span></span>  
  
|<span data-ttu-id="dcd60-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dcd60-108">HRESULT</span></span>|<span data-ttu-id="dcd60-109">Opis</span><span class="sxs-lookup"><span data-stu-id="dcd60-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dcd60-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dcd60-110">S_OK</span></span>|<span data-ttu-id="dcd60-111">`SetCLRIoCompletionManager` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="dcd60-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="dcd60-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dcd60-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dcd60-113">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="dcd60-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dcd60-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dcd60-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dcd60-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="dcd60-115">The call timed out.</span></span>|  
|<span data-ttu-id="dcd60-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dcd60-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dcd60-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="dcd60-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dcd60-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dcd60-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dcd60-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="dcd60-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dcd60-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dcd60-120">E_FAIL</span></span>|<span data-ttu-id="dcd60-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="dcd60-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dcd60-122">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="dcd60-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dcd60-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dcd60-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcd60-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dcd60-124">Remarks</span></span>  

 <span data-ttu-id="dcd60-125">Po wywołaniu środowiska CLR `SetCLRIoCompletionManager` host musi wywołać [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md) w celu powiadomienia środowiska CLR o ukończeniu żądania we/wy.</span><span class="sxs-lookup"><span data-stu-id="dcd60-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcd60-126">Wymagania</span><span class="sxs-lookup"><span data-stu-id="dcd60-126">Requirements</span></span>  

 <span data-ttu-id="dcd60-127">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcd60-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcd60-128">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dcd60-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dcd60-129">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dcd60-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dcd60-130">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcd60-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcd60-131">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="dcd60-131">See also</span></span>

- [<span data-ttu-id="dcd60-132">ICLRIoCompletionManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="dcd60-132">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="dcd60-133">IHostIoCompletionManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="dcd60-133">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
