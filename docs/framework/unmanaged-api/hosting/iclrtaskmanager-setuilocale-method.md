---
title: ICLRTaskManager::SetUILocale — Metoda
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetUILocale
helpviewer_keywords:
- ICLRTaskManager::SetUILocale method [.NET Framework hosting]
- SetUILocale method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 03adaa9a-2beb-49b3-b2c4-6b4fc3f10715
topic_type:
- apiref
ms.openlocfilehash: a426fca1b7ca4bfb9cbb30a221859f7c114db682
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732430"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="4dc0f-102">ICLRTaskManager::SetUILocale — Metoda</span><span class="sxs-lookup"><span data-stu-id="4dc0f-102">ICLRTaskManager::SetUILocale Method</span></span>

<span data-ttu-id="4dc0f-103">Powiadamia środowisko uruchomieniowe języka wspólnego (CLR) o zmodyfikowaniu przez hosta ustawień regionalnych (UI) interfejsu użytkownika lub kulturze w aktualnie wykonywanym zadaniu.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dc0f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4dc0f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dc0f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="4dc0f-105">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="4dc0f-106">podczas Wartość identyfikatora ustawień regionalnych, która jest mapowana na nowo przypisaną kulturę geograficzną i język interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4dc0f-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="4dc0f-107">Return Value</span></span>  
  
|<span data-ttu-id="4dc0f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4dc0f-108">HRESULT</span></span>|<span data-ttu-id="4dc0f-109">Opis</span><span class="sxs-lookup"><span data-stu-id="4dc0f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4dc0f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4dc0f-110">S_OK</span></span>|<span data-ttu-id="4dc0f-111">`SetUILocale` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="4dc0f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4dc0f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4dc0f-113">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4dc0f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4dc0f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4dc0f-115">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-115">The call timed out.</span></span>|  
|<span data-ttu-id="4dc0f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4dc0f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4dc0f-117">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4dc0f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4dc0f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4dc0f-119">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4dc0f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4dc0f-120">E_FAIL</span></span>|<span data-ttu-id="4dc0f-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4dc0f-122">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4dc0f-123">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4dc0f-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4dc0f-124">Remarks</span></span>  

 <span data-ttu-id="4dc0f-125">`SetUILocale` umożliwia hostowi wykonywanie wszelkich mechanizmów, które mogą być potrzebne do synchronizacji ustawień regionalnych.</span><span class="sxs-lookup"><span data-stu-id="4dc0f-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dc0f-126">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4dc0f-126">Requirements</span></span>  

 <span data-ttu-id="4dc0f-127">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dc0f-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dc0f-128">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4dc0f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4dc0f-129">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4dc0f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4dc0f-130">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dc0f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc0f-131">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4dc0f-131">See also</span></span>

- [<span data-ttu-id="4dc0f-132">ICLRTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4dc0f-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="4dc0f-133">ICLRTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4dc0f-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="4dc0f-134">IHostTask — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4dc0f-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="4dc0f-135">IHostTaskManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4dc0f-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
