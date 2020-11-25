---
title: IHostIoCompletionManager::Bind — Metoda
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.Bind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type:
- apiref
ms.openlocfilehash: 5231db8de6129ed593e4e0d508b312b7034c01f0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733909"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="c3efc-102">IHostIoCompletionManager::Bind — Metoda</span><span class="sxs-lookup"><span data-stu-id="c3efc-102">IHostIoCompletionManager::Bind Method</span></span>

<span data-ttu-id="c3efc-103">Wiąże określone dojście do portu zakończenia we/wy, który został utworzony przez wcześniejsze wywołanie do [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="c3efc-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3efc-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c3efc-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3efc-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c3efc-105">Parameters</span></span>  

 `hPort`  
 <span data-ttu-id="c3efc-106">podczas Port zakończenia we/wy, do którego ma zostać utworzone powiązanie `hHandle` .</span><span class="sxs-lookup"><span data-stu-id="c3efc-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="c3efc-107">Jeśli wartość `hPort` jest równa null, `hHandle` jest powiązana z domyślnym portem zakończenia operacji we/wy.</span><span class="sxs-lookup"><span data-stu-id="c3efc-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="c3efc-108">podczas Dojście systemu operacyjnego, z którym ma zostać utworzone powiązanie `hPort` .</span><span class="sxs-lookup"><span data-stu-id="c3efc-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3efc-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c3efc-109">Return Value</span></span>  
  
|<span data-ttu-id="c3efc-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c3efc-110">HRESULT</span></span>|<span data-ttu-id="c3efc-111">Opis</span><span class="sxs-lookup"><span data-stu-id="c3efc-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3efc-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3efc-112">S_OK</span></span>|<span data-ttu-id="c3efc-113">`Bind` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="c3efc-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="c3efc-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c3efc-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c3efc-115">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="c3efc-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c3efc-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c3efc-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c3efc-117">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="c3efc-117">The call timed out.</span></span>|  
|<span data-ttu-id="c3efc-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c3efc-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c3efc-119">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="c3efc-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c3efc-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c3efc-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c3efc-121">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="c3efc-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c3efc-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c3efc-122">E_FAIL</span></span>|<span data-ttu-id="c3efc-123">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="c3efc-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c3efc-124">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="c3efc-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c3efc-125">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c3efc-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3efc-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c3efc-126">Remarks</span></span>  

 <span data-ttu-id="c3efc-127">Port zakończenia we/wy jest tworzony przy użyciu wywołania do `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="c3efc-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="c3efc-128">Środowisko CLR wywołuje `Bind` powiązanie z dojściem do tego portu.</span><span class="sxs-lookup"><span data-stu-id="c3efc-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3efc-129">Po zakończeniu żądania we/wy host musi wywołać metodę [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c3efc-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3efc-130">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c3efc-130">Requirements</span></span>  

 <span data-ttu-id="c3efc-131">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3efc-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3efc-132">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c3efc-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3efc-133">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c3efc-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3efc-134">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3efc-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3efc-135">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c3efc-135">See also</span></span>

- [<span data-ttu-id="c3efc-136">ICLRIoCompletionManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c3efc-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
