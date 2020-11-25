---
title: IHostThreadPoolManager::GetAvailableThreads — Metoda
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
ms.openlocfilehash: 64d5ba9ad5557f99b175c277d48003529d77861c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730815"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="1cfd9-102">IHostThreadPoolManager::GetAvailableThreads — Metoda</span><span class="sxs-lookup"><span data-stu-id="1cfd9-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>

<span data-ttu-id="1cfd9-103">Pobiera liczbę wątków w puli wątków, które nie przetwarzają obecnie elementów roboczych.</span><span class="sxs-lookup"><span data-stu-id="1cfd9-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cfd9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1cfd9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cfd9-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="1cfd9-105">Parameters</span></span>  

 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="1cfd9-106">określoną Wskaźnik do liczby wątków w puli wątków, które nie przetwarzają obecnie elementów roboczych.</span><span class="sxs-lookup"><span data-stu-id="1cfd9-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1cfd9-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="1cfd9-107">Return Value</span></span>  
  
|<span data-ttu-id="1cfd9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1cfd9-108">HRESULT</span></span>|<span data-ttu-id="1cfd9-109">Opis</span><span class="sxs-lookup"><span data-stu-id="1cfd9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1cfd9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1cfd9-110">S_OK</span></span>|<span data-ttu-id="1cfd9-111">`GetAvailableThreads` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="1cfd9-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="1cfd9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1cfd9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1cfd9-113">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="1cfd9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1cfd9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1cfd9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1cfd9-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="1cfd9-115">The call timed out.</span></span>|  
|<span data-ttu-id="1cfd9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1cfd9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1cfd9-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="1cfd9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1cfd9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1cfd9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1cfd9-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="1cfd9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1cfd9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1cfd9-120">E_FAIL</span></span>|<span data-ttu-id="1cfd9-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="1cfd9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1cfd9-122">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="1cfd9-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1cfd9-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1cfd9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1cfd9-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="1cfd9-124">E_NOTIMPL</span></span>|<span data-ttu-id="1cfd9-125">Host nie oferuje implementacji programu `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="1cfd9-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cfd9-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1cfd9-126">Remarks</span></span>  

 <span data-ttu-id="1cfd9-127">Jeśli host nie dostarcza implementacji `GetAvailableThreads` , powinien zwrócić wartość HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="1cfd9-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cfd9-128">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1cfd9-128">Requirements</span></span>  

 <span data-ttu-id="1cfd9-129">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cfd9-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cfd9-130">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1cfd9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1cfd9-131">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1cfd9-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1cfd9-132">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cfd9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cfd9-133">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1cfd9-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="1cfd9-134">IHostThreadPoolManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="1cfd9-134">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
