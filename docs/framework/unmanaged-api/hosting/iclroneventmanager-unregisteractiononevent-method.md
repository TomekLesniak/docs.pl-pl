---
title: ICLROnEventManager::UnregisterActionOnEvent — Metoda
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.UnregisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::UnregisterActionOnEvent
helpviewer_keywords:
- UnRegisterActionOnEvent method [.NET Framework hosting]
- ICLROnEventManager::UnRegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: 4c02ec37-cdf0-46b2-890e-235092741236
topic_type:
- apiref
ms.openlocfilehash: ca3c7fe813f22d3beab3087414100b3d8e5814ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725602"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="831af-102">ICLROnEventManager::UnregisterActionOnEvent — Metoda</span><span class="sxs-lookup"><span data-stu-id="831af-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>

<span data-ttu-id="831af-103">Wyrejestrowuje wcześniej zarejestrowany wskaźnik wywołania zwrotnego dla określonego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="831af-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="831af-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="831af-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="831af-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="831af-105">Parameters</span></span>  

 `event`  
 <span data-ttu-id="831af-106">podczas Jedna z wartości [EClrEvent —](eclrevent-enumeration.md) , wskazująca na zdarzenie, dla którego ma zostać wyrejestrowany wskaźnik wywołania zwrotnego opisany przez `pAction` .</span><span class="sxs-lookup"><span data-stu-id="831af-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="831af-107">podczas Wskaźnik do obiektu [IActionOnCLREvent](iactiononclrevent-interface.md) , który został przekazano jako parametr do metody [RegisterActionOnEvent —](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="831af-107">[in] A pointer to an [IActionOnCLREvent](iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="831af-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="831af-108">Return Value</span></span>  
  
|<span data-ttu-id="831af-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="831af-109">HRESULT</span></span>|<span data-ttu-id="831af-110">Opis</span><span class="sxs-lookup"><span data-stu-id="831af-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="831af-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="831af-111">S_OK</span></span>|<span data-ttu-id="831af-112">`UnregisterActionOnEvent` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="831af-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="831af-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="831af-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="831af-114">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="831af-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="831af-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="831af-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="831af-116">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="831af-116">The call timed out.</span></span>|  
|<span data-ttu-id="831af-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="831af-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="831af-118">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="831af-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="831af-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="831af-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="831af-120">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="831af-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="831af-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="831af-121">E_FAIL</span></span>|<span data-ttu-id="831af-122">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="831af-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="831af-123">Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie.</span><span class="sxs-lookup"><span data-stu-id="831af-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="831af-124">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="831af-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="831af-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="831af-125">Requirements</span></span>  

 <span data-ttu-id="831af-126">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="831af-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="831af-127">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="831af-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="831af-128">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="831af-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="831af-129">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="831af-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="831af-130">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="831af-130">See also</span></span>

- [<span data-ttu-id="831af-131">EClrEvent — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="831af-131">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="831af-132">IActionOnCLREvent — Interfejs</span><span class="sxs-lookup"><span data-stu-id="831af-132">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="831af-133">ICLRControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="831af-133">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="831af-134">ICLROnEventManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="831af-134">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
