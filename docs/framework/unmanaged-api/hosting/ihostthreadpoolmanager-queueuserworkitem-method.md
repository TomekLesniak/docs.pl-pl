---
title: IHostThreadPoolManager::QueueUserWorkItem — Metoda
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.QueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type:
- apiref
ms.openlocfilehash: 4537d367518dd80b2559f8ca058684e234ff7a91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730750"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="d9580-102">IHostThreadPoolManager::QueueUserWorkItem — Metoda</span><span class="sxs-lookup"><span data-stu-id="d9580-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>

<span data-ttu-id="d9580-103">Kolejkuje funkcję do wykonania i określa obiekt zawierający dane, które mają być używane przez tę funkcję.</span><span class="sxs-lookup"><span data-stu-id="d9580-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="d9580-104">Funkcja jest wykonywana po udostępnieniu wątku.</span><span class="sxs-lookup"><span data-stu-id="d9580-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9580-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="d9580-105">Syntax</span></span>  
  
```cpp  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9580-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="d9580-106">Parameters</span></span>  

 `Function`  
 <span data-ttu-id="d9580-107">podczas Wskaźnik funkcji, który reprezentuje funkcję do wykonania.</span><span class="sxs-lookup"><span data-stu-id="d9580-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="d9580-108">podczas Obiekt, który zawiera dane, które mają być używane przez `Function` .</span><span class="sxs-lookup"><span data-stu-id="d9580-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="d9580-109">podczas Jedna z wartości flag, zgodnie z definicją dla `QueueUserWorkItem` metody Win32, która kontroluje wykonanie.</span><span class="sxs-lookup"><span data-stu-id="d9580-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9580-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="d9580-110">Return Value</span></span>  
  
|<span data-ttu-id="d9580-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9580-111">HRESULT</span></span>|<span data-ttu-id="d9580-112">Opis</span><span class="sxs-lookup"><span data-stu-id="d9580-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9580-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9580-113">S_OK</span></span>|<span data-ttu-id="d9580-114">`QueueUserWorkItem` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="d9580-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="d9580-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d9580-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d9580-116">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="d9580-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d9580-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d9580-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d9580-118">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="d9580-118">The call timed out.</span></span>|  
|<span data-ttu-id="d9580-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9580-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d9580-120">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="d9580-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d9580-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d9580-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d9580-122">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="d9580-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d9580-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d9580-123">E_FAIL</span></span>|<span data-ttu-id="d9580-124">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="d9580-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d9580-125">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="d9580-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d9580-126">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d9580-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9580-127">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d9580-127">Remarks</span></span>  

 <span data-ttu-id="d9580-128">`QueueUserWorkItem` kolejkuje element roboczy do wątku roboczego w puli wątków.</span><span class="sxs-lookup"><span data-stu-id="d9580-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="d9580-129">Jego sygnatura i typy parametrów są identyczne z odpowiednimi funkcjami Win32, które mają taką samą nazwę.</span><span class="sxs-lookup"><span data-stu-id="d9580-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="d9580-130">Aby uzyskać więcej informacji, zobacz dokumentację platformy systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="d9580-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9580-131">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d9580-131">Requirements</span></span>  

 <span data-ttu-id="d9580-132">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9580-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9580-133">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d9580-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9580-134">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d9580-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9580-135">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9580-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9580-136">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d9580-136">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="d9580-137">IHostThreadPoolManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d9580-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
