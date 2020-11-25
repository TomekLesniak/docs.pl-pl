---
title: IHostSyncManager::CreateRWLockWriterEvent — Metoda
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockWriterEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockWriterEvent
helpviewer_keywords:
- CreateRWLockWriterEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockWriterEvent method [.NET Framework hosting]
ms.assetid: 70e488c2-cf53-4dc0-ba52-74372d215c41
topic_type:
- apiref
ms.openlocfilehash: 5b5faf14337f78d9b176787528ae8947f5810ba6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704373"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="52ce8-102">IHostSyncManager::CreateRWLockWriterEvent — Metoda</span><span class="sxs-lookup"><span data-stu-id="52ce8-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>

<span data-ttu-id="52ce8-103">Tworzy obiekt zdarzenia autoresetowania dla implementacji blokady składnika zapisywania.</span><span class="sxs-lookup"><span data-stu-id="52ce8-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ce8-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="52ce8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52ce8-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="52ce8-105">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="52ce8-106">podczas Plik cookie, który ma zostać skojarzony ze zdarzeniem resetowania.</span><span class="sxs-lookup"><span data-stu-id="52ce8-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="52ce8-107">określoną Wskaźnik do adresu wystąpienia [IHostAutoEvent](ihostautoevent-interface.md) lub wartość null, jeśli nie można utworzyć obiektu zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="52ce8-107">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52ce8-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="52ce8-108">Return Value</span></span>  
  
|<span data-ttu-id="52ce8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52ce8-109">HRESULT</span></span>|<span data-ttu-id="52ce8-110">Opis</span><span class="sxs-lookup"><span data-stu-id="52ce8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52ce8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="52ce8-111">S_OK</span></span>|<span data-ttu-id="52ce8-112">`CreateRWLockWriterEvent` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="52ce8-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="52ce8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="52ce8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="52ce8-114">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="52ce8-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="52ce8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="52ce8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="52ce8-116">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="52ce8-116">The call timed out.</span></span>|  
|<span data-ttu-id="52ce8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="52ce8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="52ce8-118">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="52ce8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="52ce8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="52ce8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="52ce8-120">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="52ce8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="52ce8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52ce8-121">E_FAIL</span></span>|<span data-ttu-id="52ce8-122">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="52ce8-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="52ce8-123">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="52ce8-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="52ce8-124">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="52ce8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="52ce8-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="52ce8-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="52ce8-126">Za mało dostępnej pamięci, aby utworzyć żądany obiekt zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="52ce8-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52ce8-127">Uwagi</span><span class="sxs-lookup"><span data-stu-id="52ce8-127">Remarks</span></span>  

 <span data-ttu-id="52ce8-128">Środowisko CLR wywołuje `CreateRWLockWriterEvent` metodę, aby uzyskać odwołanie do wystąpienia, `IHostAutoEvent` które ma być używane w jego implementacji blokady składnika zapisywania.</span><span class="sxs-lookup"><span data-stu-id="52ce8-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="52ce8-129">Host może użyć określonego pliku cookie, aby określić, które zadania oczekują na blokadę, wywołując metody iteracji interfejsu [ICLRSyncManager](iclrsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="52ce8-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52ce8-130">Wymagania</span><span class="sxs-lookup"><span data-stu-id="52ce8-130">Requirements</span></span>  

 <span data-ttu-id="52ce8-131">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52ce8-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52ce8-132">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="52ce8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52ce8-133">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="52ce8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52ce8-134">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52ce8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52ce8-135">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="52ce8-135">See also</span></span>

- [<span data-ttu-id="52ce8-136">ICLRSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="52ce8-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="52ce8-137">IHostAutoEvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="52ce8-137">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="52ce8-138">IHostManualEvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="52ce8-138">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="52ce8-139">IHostSyncManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="52ce8-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
