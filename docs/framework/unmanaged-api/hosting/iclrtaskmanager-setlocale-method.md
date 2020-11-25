---
title: ICLRTaskManager::SetLocale — Metoda
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: ed16bb7f-4206-43a8-b9e9-c5737b69e3af
topic_type:
- apiref
ms.openlocfilehash: 5f799c140705a5279c996b6bec90ab1f29bd42ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732440"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="b07c5-102">ICLRTaskManager::SetLocale — Metoda</span><span class="sxs-lookup"><span data-stu-id="b07c5-102">ICLRTaskManager::SetLocale Method</span></span>

<span data-ttu-id="b07c5-103">Powiadamia środowisko uruchomieniowe języka wspólnego (CLR), że host zmodyfikował wartość identyfikatora ustawień regionalnych (która jest mapowana na kulturę geograficzną i język) w aktualnie wykonywanym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="b07c5-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b07c5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b07c5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b07c5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b07c5-105">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="b07c5-106">podczas Wartość identyfikatora ustawień regionalnych, która jest mapowana na nowo przypisaną kulturę geograficzną i język.</span><span class="sxs-lookup"><span data-stu-id="b07c5-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b07c5-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="b07c5-107">Return Value</span></span>  
  
|<span data-ttu-id="b07c5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b07c5-108">HRESULT</span></span>|<span data-ttu-id="b07c5-109">Opis</span><span class="sxs-lookup"><span data-stu-id="b07c5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b07c5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b07c5-110">S_OK</span></span>|<span data-ttu-id="b07c5-111">Metoda została pomyślnie zwrócona.</span><span class="sxs-lookup"><span data-stu-id="b07c5-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="b07c5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b07c5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b07c5-113">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="b07c5-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b07c5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b07c5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b07c5-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="b07c5-115">The call timed out.</span></span>|  
|<span data-ttu-id="b07c5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b07c5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b07c5-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="b07c5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b07c5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b07c5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b07c5-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="b07c5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b07c5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b07c5-120">E_FAIL</span></span>|<span data-ttu-id="b07c5-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="b07c5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b07c5-122">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="b07c5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b07c5-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b07c5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b07c5-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b07c5-124">Remarks</span></span>  

 <span data-ttu-id="b07c5-125">`SetLocale` zapewnia hostowi możliwość wykonywania wszelkich mechanizmów, które mogą być potrzebne do synchronizacji ustawień regionalnych.</span><span class="sxs-lookup"><span data-stu-id="b07c5-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b07c5-126">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b07c5-126">Requirements</span></span>  

 <span data-ttu-id="b07c5-127">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b07c5-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b07c5-128">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b07c5-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b07c5-129">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b07c5-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b07c5-130">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b07c5-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b07c5-131">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b07c5-131">See also</span></span>

- [<span data-ttu-id="b07c5-132">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b07c5-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="b07c5-133">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b07c5-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="b07c5-134">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b07c5-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="b07c5-135">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b07c5-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
