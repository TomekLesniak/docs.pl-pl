---
title: ICLRTaskManager::CreateTask — Metoda
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
ms.openlocfilehash: c8d18b78cf0185271eae763892610d13f76e42ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734000"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="6113d-102">ICLRTaskManager::CreateTask — Metoda</span><span class="sxs-lookup"><span data-stu-id="6113d-102">ICLRTaskManager::CreateTask Method</span></span>

<span data-ttu-id="6113d-103">Żądania jawnie, które tworzą nowe zadanie środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="6113d-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6113d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6113d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6113d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="6113d-105">Parameters</span></span>  

 `pTask`  
 <span data-ttu-id="6113d-106">określoną Wskaźnik na adres nowo utworzonego [ICLRTask](iclrtask-interface.md)lub wartość null, jeśli nie można utworzyć zadania.</span><span class="sxs-lookup"><span data-stu-id="6113d-106">[out] A pointer to the address of a newly created [ICLRTask](iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6113d-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="6113d-107">Return Value</span></span>  
  
|<span data-ttu-id="6113d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6113d-108">HRESULT</span></span>|<span data-ttu-id="6113d-109">Opis</span><span class="sxs-lookup"><span data-stu-id="6113d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6113d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6113d-110">S_OK</span></span>|<span data-ttu-id="6113d-111">Metoda została pomyślnie zwrócona.</span><span class="sxs-lookup"><span data-stu-id="6113d-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="6113d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6113d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6113d-113">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="6113d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6113d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6113d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6113d-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="6113d-115">The call timed out.</span></span>|  
|<span data-ttu-id="6113d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6113d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6113d-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="6113d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6113d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6113d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6113d-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="6113d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6113d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6113d-120">E_FAIL</span></span>|<span data-ttu-id="6113d-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="6113d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6113d-122">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="6113d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6113d-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6113d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6113d-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6113d-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6113d-125">Za mało dostępnej pamięci, aby przydzielić żądany zasób.</span><span class="sxs-lookup"><span data-stu-id="6113d-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6113d-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6113d-126">Remarks</span></span>  

 <span data-ttu-id="6113d-127">Środowisko CLR tworzy nowe zadanie automatycznie po zainicjowaniu, gdy kod użytkownika tworzy wątek przy użyciu typów w <xref:System.Threading> przestrzeni nazw lub zwiększenie rozmiaru puli wątków.</span><span class="sxs-lookup"><span data-stu-id="6113d-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="6113d-128">Tworzy również zadania, gdy kod niezarządzany wykonuje wywołanie do funkcji zarządzanej.</span><span class="sxs-lookup"><span data-stu-id="6113d-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="6113d-129">`CreateTask` umożliwia hostowi jawne żądanie utworzenia nowego zadania przez środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="6113d-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="6113d-130">Na przykład host może wywołać tę metodę, aby wstępnie zainicjować struktury danych.</span><span class="sxs-lookup"><span data-stu-id="6113d-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6113d-131">Nowe zadanie jest zwracane w stanie wstrzymania i pozostaje zawieszone, dopóki Host jawnie wywoła [IHostTask:: Start](ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="6113d-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6113d-132">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6113d-132">Requirements</span></span>  

 <span data-ttu-id="6113d-133">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6113d-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6113d-134">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6113d-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6113d-135">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6113d-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6113d-136">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6113d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6113d-137">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6113d-137">See also</span></span>

- [<span data-ttu-id="6113d-138">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6113d-138">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="6113d-139">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6113d-139">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="6113d-140">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6113d-140">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="6113d-141">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6113d-141">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
