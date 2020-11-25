---
title: IHostTaskManager::Sleep — Metoda
ms.date: 03/30/2017
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
ms.openlocfilehash: 372b15a565f8a7484c1c42c387098a38f7bbf428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702059"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="c67d3-102">IHostTaskManager::Sleep — Metoda</span><span class="sxs-lookup"><span data-stu-id="c67d3-102">IHostTaskManager::Sleep Method</span></span>

<span data-ttu-id="c67d3-103">Powiadamia hosta, że bieżące zadanie przechodzi w stan uśpienia.</span><span class="sxs-lookup"><span data-stu-id="c67d3-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c67d3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c67d3-104">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c67d3-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c67d3-105">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="c67d3-106">podczas Przedział czasu (w milisekundach), przez który wątek będzie uśpiony.</span><span class="sxs-lookup"><span data-stu-id="c67d3-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="c67d3-107">podczas Jedna z wartości wyliczenia [WAIT_OPTION](wait-option-enumeration.md) wskazująca, jaka akcja powinna być wykonywana przez hosta, jeśli ta akcja jest blokowana.</span><span class="sxs-lookup"><span data-stu-id="c67d3-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c67d3-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c67d3-108">Return Value</span></span>  
  
|<span data-ttu-id="c67d3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c67d3-109">HRESULT</span></span>|<span data-ttu-id="c67d3-110">Opis</span><span class="sxs-lookup"><span data-stu-id="c67d3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c67d3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c67d3-111">S_OK</span></span>|<span data-ttu-id="c67d3-112">`Sleep` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="c67d3-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="c67d3-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c67d3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c67d3-114">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="c67d3-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c67d3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c67d3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c67d3-116">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="c67d3-116">The call timed out.</span></span>|  
|<span data-ttu-id="c67d3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c67d3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c67d3-118">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="c67d3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c67d3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c67d3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c67d3-120">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="c67d3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c67d3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c67d3-121">E_FAIL</span></span>|<span data-ttu-id="c67d3-122">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="c67d3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c67d3-123">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="c67d3-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c67d3-124">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c67d3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c67d3-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c67d3-125">Remarks</span></span>  

 <span data-ttu-id="c67d3-126">Środowisko CLR zwykle wywołuje `IHostTaskManager::Sleep` metodę, gdy <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> jest wywoływana z kodu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c67d3-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c67d3-127">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c67d3-127">Requirements</span></span>  

 <span data-ttu-id="c67d3-128">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c67d3-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c67d3-129">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c67d3-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c67d3-130">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c67d3-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c67d3-131">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c67d3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c67d3-132">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c67d3-132">See also</span></span>

- [<span data-ttu-id="c67d3-133">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c67d3-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c67d3-134">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c67d3-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c67d3-135">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c67d3-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c67d3-136">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c67d3-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
