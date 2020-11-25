---
title: IHostThreadPoolManager::SetMaxThreads — Metoda
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type:
- apiref
ms.openlocfilehash: 68e806daa63d13ad6c1f3b5de634c20ca02e8eb4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730721"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="e8b6b-102">IHostThreadPoolManager::SetMaxThreads — Metoda</span><span class="sxs-lookup"><span data-stu-id="e8b6b-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>

<span data-ttu-id="e8b6b-103">Ustawia maksymalną liczbę wątków, które host może przechowywać w puli wątków.</span><span class="sxs-lookup"><span data-stu-id="e8b6b-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8b6b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e8b6b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8b6b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e8b6b-105">Parameters</span></span>  

 `MaxThreads`  
 <span data-ttu-id="e8b6b-106">Maksymalna liczba wątków roboczych w puli wątków.</span><span class="sxs-lookup"><span data-stu-id="e8b6b-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8b6b-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="e8b6b-107">Return Value</span></span>  
  
|<span data-ttu-id="e8b6b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e8b6b-108">HRESULT</span></span>|<span data-ttu-id="e8b6b-109">Opis</span><span class="sxs-lookup"><span data-stu-id="e8b6b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e8b6b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e8b6b-110">S_OK</span></span>|<span data-ttu-id="e8b6b-111">`SetMaxThreads` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="e8b6b-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="e8b6b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e8b6b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e8b6b-113">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="e8b6b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e8b6b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e8b6b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e8b6b-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="e8b6b-115">The call timed out.</span></span>|  
|<span data-ttu-id="e8b6b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e8b6b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e8b6b-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="e8b6b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e8b6b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e8b6b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e8b6b-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="e8b6b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e8b6b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e8b6b-120">E_FAIL</span></span>|<span data-ttu-id="e8b6b-121">Wystąpił nieznany, Katastrofalny błąd.</span><span class="sxs-lookup"><span data-stu-id="e8b6b-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e8b6b-122">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="e8b6b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e8b6b-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e8b6b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e8b6b-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e8b6b-124">E_NOTIMPL</span></span>|<span data-ttu-id="e8b6b-125">Host nie oferuje implementacji programu `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="e8b6b-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8b6b-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e8b6b-126">Remarks</span></span>  

 <span data-ttu-id="e8b6b-127">Host nie jest wymagany, aby umożliwić programowi CLR skonfigurowanie rozmiaru puli wątków.</span><span class="sxs-lookup"><span data-stu-id="e8b6b-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="e8b6b-128">Niektóre hosty mogą mieć wyłączną kontrolę nad pulą wątków, z przyczyn takich jak implementacja, wydajność lub skalowalność.</span><span class="sxs-lookup"><span data-stu-id="e8b6b-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="e8b6b-129">W takim przypadku host powinien zwrócić wartość HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="e8b6b-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8b6b-130">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e8b6b-130">Requirements</span></span>  

 <span data-ttu-id="e8b6b-131">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8b6b-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8b6b-132">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e8b6b-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8b6b-133">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e8b6b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8b6b-134">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8b6b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8b6b-135">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e8b6b-135">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="e8b6b-136">GetMaxThreads, metoda</span><span class="sxs-lookup"><span data-stu-id="e8b6b-136">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="e8b6b-137">SetMinThreads, metoda</span><span class="sxs-lookup"><span data-stu-id="e8b6b-137">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="e8b6b-138">IHostThreadPoolManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e8b6b-138">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
