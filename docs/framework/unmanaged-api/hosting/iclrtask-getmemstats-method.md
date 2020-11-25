---
title: ICLRTask::GetMemStats — Metoda
ms.date: 03/30/2017
api_name:
- ICLRTask.GetMemStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type:
- apiref
ms.openlocfilehash: 5d57bc742ebcba00f9fbe569a4be27b82a5f8055
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726512"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="e62de-102">ICLRTask::GetMemStats — Metoda</span><span class="sxs-lookup"><span data-stu-id="e62de-102">ICLRTask::GetMemStats Method</span></span>

<span data-ttu-id="e62de-103">Pobiera statystyczne informacje o wykorzystaniu pamięci powiązane z zadaniem, które reprezentuje bieżące wystąpienie [ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e62de-103">Gets statistical memory usage information related to the task that the current [ICLRTask](iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e62de-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e62de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e62de-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e62de-105">Parameters</span></span>  

 `pMemUsage`  
 <span data-ttu-id="e62de-106">określoną Wskaźnik do wystąpienia [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) , który zawiera szczegółowe informacje o użyciu pamięci zadania, w tym liczbę przydzieloną bajtów.</span><span class="sxs-lookup"><span data-stu-id="e62de-106">[out] A pointer to a [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e62de-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="e62de-107">Return Value</span></span>  
  
|<span data-ttu-id="e62de-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e62de-108">HRESULT</span></span>|<span data-ttu-id="e62de-109">Opis</span><span class="sxs-lookup"><span data-stu-id="e62de-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e62de-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e62de-110">S_OK</span></span>|<span data-ttu-id="e62de-111">`GetMemStats` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="e62de-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="e62de-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e62de-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e62de-113">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="e62de-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e62de-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e62de-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e62de-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="e62de-115">The call timed out.</span></span>|  
|<span data-ttu-id="e62de-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e62de-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e62de-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="e62de-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e62de-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e62de-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e62de-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="e62de-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e62de-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e62de-120">E_FAIL</span></span>|<span data-ttu-id="e62de-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="e62de-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e62de-122">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="e62de-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e62de-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e62de-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e62de-124">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e62de-124">Requirements</span></span>  

 <span data-ttu-id="e62de-125">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e62de-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e62de-126">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e62de-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e62de-127">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e62de-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e62de-128">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e62de-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e62de-129">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e62de-129">See also</span></span>

- [<span data-ttu-id="e62de-130">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e62de-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="e62de-131">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e62de-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="e62de-132">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e62de-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="e62de-133">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e62de-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
