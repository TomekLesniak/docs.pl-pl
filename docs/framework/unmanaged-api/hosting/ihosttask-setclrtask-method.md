---
title: IHostTask::SetCLRTask — Metoda
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
ms.openlocfilehash: e6b9a4015a6139d6c8d7101fa7811c7ad9134e4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720467"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="5f81e-102">IHostTask::SetCLRTask — Metoda</span><span class="sxs-lookup"><span data-stu-id="5f81e-102">IHostTask::SetCLRTask Method</span></span>

<span data-ttu-id="5f81e-103">Kojarzy `ICLRTask` wystąpienie z bieżącym wystąpieniem [IHostTask](ihosttask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5f81e-103">Associates an `ICLRTask` instance with the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f81e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5f81e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f81e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="5f81e-105">Parameters</span></span>  

 `pCLRTask`  
 <span data-ttu-id="5f81e-106">podczas Wskaźnik interfejsu do wystąpienia, `ICLRTask` które ma zostać skojarzone z bieżącym `IHostTask` wystąpieniem.</span><span class="sxs-lookup"><span data-stu-id="5f81e-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f81e-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="5f81e-107">Return Value</span></span>  
  
|<span data-ttu-id="5f81e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5f81e-108">HRESULT</span></span>|<span data-ttu-id="5f81e-109">Opis</span><span class="sxs-lookup"><span data-stu-id="5f81e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5f81e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f81e-110">S_OK</span></span>|<span data-ttu-id="5f81e-111">`SetCLRTask` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="5f81e-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="5f81e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5f81e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5f81e-113">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="5f81e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5f81e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5f81e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5f81e-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="5f81e-115">The call timed out.</span></span>|  
|<span data-ttu-id="5f81e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5f81e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5f81e-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="5f81e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5f81e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5f81e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5f81e-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="5f81e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5f81e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5f81e-120">E_FAIL</span></span>|<span data-ttu-id="5f81e-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="5f81e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5f81e-122">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="5f81e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5f81e-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5f81e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f81e-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5f81e-124">Remarks</span></span>  

 <span data-ttu-id="5f81e-125">Środowisko CLR wywołuje `SetCLRTask` skojarzenie `ICLRTask` wystąpienia z bieżącym `IHostTask` wystąpieniem, które zostało utworzone przez wywołanie [IHostTaskManager::](ihosttaskmanager-createtask-method.md)CreateInstance.</span><span class="sxs-lookup"><span data-stu-id="5f81e-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f81e-126">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5f81e-126">Requirements</span></span>  

 <span data-ttu-id="5f81e-127">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f81e-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f81e-128">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5f81e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f81e-129">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f81e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f81e-130">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f81e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f81e-131">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5f81e-131">See also</span></span>

- [<span data-ttu-id="5f81e-132">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5f81e-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="5f81e-133">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5f81e-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="5f81e-134">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5f81e-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="5f81e-135">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5f81e-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
