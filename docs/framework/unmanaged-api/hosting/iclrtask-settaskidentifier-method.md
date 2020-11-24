---
title: ICLRTask::SetTaskIdentifier — Metoda
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
ms.openlocfilehash: d1f731e00d4917b997dfba392cb9b6ce2afc082e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690749"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="69cbc-102">ICLRTask::SetTaskIdentifier — Metoda</span><span class="sxs-lookup"><span data-stu-id="69cbc-102">ICLRTask::SetTaskIdentifier Method</span></span>

<span data-ttu-id="69cbc-103">Instruuje środowisko uruchomieniowe języka wspólnego (CLR), aby skojarzyć określoną wartość identyfikatora z zadaniem reprezentowanem przez bieżące wystąpienie [ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="69cbc-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69cbc-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="69cbc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69cbc-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="69cbc-105">Parameters</span></span>  

 `Asked`  
 <span data-ttu-id="69cbc-106">podczas Unikatowy identyfikator środowiska uruchomieniowego języka wspólnego, który ma zostać skojarzony z zadaniem reprezentowanym przez bieżące `ICLRTask` wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="69cbc-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69cbc-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="69cbc-107">Return Value</span></span>  
  
|<span data-ttu-id="69cbc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="69cbc-108">HRESULT</span></span>|<span data-ttu-id="69cbc-109">Opis</span><span class="sxs-lookup"><span data-stu-id="69cbc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="69cbc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="69cbc-110">S_OK</span></span>|<span data-ttu-id="69cbc-111">`SetTaskIdentifier` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="69cbc-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="69cbc-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="69cbc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="69cbc-113">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="69cbc-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="69cbc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="69cbc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="69cbc-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="69cbc-115">The call timed out.</span></span>|  
|<span data-ttu-id="69cbc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="69cbc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="69cbc-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="69cbc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="69cbc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="69cbc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="69cbc-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="69cbc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="69cbc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="69cbc-120">E_FAIL</span></span>|<span data-ttu-id="69cbc-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="69cbc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="69cbc-122">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="69cbc-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="69cbc-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="69cbc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69cbc-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="69cbc-124">Remarks</span></span>  

 <span data-ttu-id="69cbc-125">Host może skojarzyć identyfikator z zadaniem, aby ułatwić integrację środowiska CLR i hosta w środowisku debugowania.</span><span class="sxs-lookup"><span data-stu-id="69cbc-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="69cbc-126">Identyfikator nie ma znaczenia dla środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="69cbc-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="69cbc-127">Środowisko CLR przekazuje go do aplikacji debugera.</span><span class="sxs-lookup"><span data-stu-id="69cbc-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="69cbc-128">Debuger może użyć tego identyfikatora, aby skojarzyć stos wywołań CLR z stosem wywołań hosta i włączyć odpowiednie informacje śledzenia, które mają być ujednolicone podczas wyświetlania w interfejsie użytkownika debugera.</span><span class="sxs-lookup"><span data-stu-id="69cbc-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69cbc-129">Wymagania</span><span class="sxs-lookup"><span data-stu-id="69cbc-129">Requirements</span></span>  

 <span data-ttu-id="69cbc-130">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69cbc-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69cbc-131">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="69cbc-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69cbc-132">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69cbc-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69cbc-133">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69cbc-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69cbc-134">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="69cbc-134">See also</span></span>

- [<span data-ttu-id="69cbc-135">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="69cbc-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="69cbc-136">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="69cbc-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="69cbc-137">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="69cbc-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="69cbc-138">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="69cbc-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
