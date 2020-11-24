---
title: ICLRTask::RudeAbort — Metoda
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
ms.openlocfilehash: 5b0e2265810b00fe0760d4e25c0f9904a96d9f2a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691051"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="9ec57-102">ICLRTask::RudeAbort — Metoda</span><span class="sxs-lookup"><span data-stu-id="9ec57-102">ICLRTask::RudeAbort Method</span></span>

<span data-ttu-id="9ec57-103">Instruuje środowisko uruchomieniowe języka wspólnego (CLR), aby przerwać zadanie reprezentowane przez bieżące wystąpienie [interfejsu ICLRTask](iclrtask-interface.md) od razu i bezwarunkowo.</span><span class="sxs-lookup"><span data-stu-id="9ec57-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ec57-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9ec57-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="9ec57-105">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="9ec57-105">Return Value</span></span>  
  
|<span data-ttu-id="9ec57-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ec57-106">HRESULT</span></span>|<span data-ttu-id="9ec57-107">Opis</span><span class="sxs-lookup"><span data-stu-id="9ec57-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ec57-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ec57-108">S_OK</span></span>|<span data-ttu-id="9ec57-109">`RudeAbort` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="9ec57-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="9ec57-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9ec57-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9ec57-111">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="9ec57-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9ec57-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9ec57-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9ec57-113">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="9ec57-113">The call timed out.</span></span>|  
|<span data-ttu-id="9ec57-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ec57-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9ec57-115">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="9ec57-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9ec57-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9ec57-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9ec57-117">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="9ec57-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9ec57-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9ec57-118">E_FAIL</span></span>|<span data-ttu-id="9ec57-119">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="9ec57-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9ec57-120">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="9ec57-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9ec57-121">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9ec57-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ec57-122">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9ec57-122">Remarks</span></span>  

 <span data-ttu-id="9ec57-123">Host wywołuje, `RudeAbort` Aby natychmiast przerwać zadanie.</span><span class="sxs-lookup"><span data-stu-id="9ec57-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="9ec57-124">Finalizatory i procedury obsługi wyjątków nie są gwarantowane.</span><span class="sxs-lookup"><span data-stu-id="9ec57-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ec57-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9ec57-125">Requirements</span></span>  

 <span data-ttu-id="9ec57-126">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ec57-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ec57-127">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9ec57-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ec57-128">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ec57-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ec57-129">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ec57-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec57-130">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9ec57-130">See also</span></span>

- [<span data-ttu-id="9ec57-131">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9ec57-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="9ec57-132">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9ec57-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="9ec57-133">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9ec57-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="9ec57-134">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9ec57-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
