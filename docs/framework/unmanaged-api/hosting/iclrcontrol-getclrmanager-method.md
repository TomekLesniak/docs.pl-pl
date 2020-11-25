---
title: ICLRControl::GetCLRManager — Metoda
ms.date: 03/30/2017
api_name:
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
ms.openlocfilehash: d18b3a5c06ac0d3a86f7823f3b140c76c6c9a746
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728358"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="2f651-102">ICLRControl::GetCLRManager — Metoda</span><span class="sxs-lookup"><span data-stu-id="2f651-102">ICLRControl::GetCLRManager Method</span></span>

<span data-ttu-id="2f651-103">Pobiera wskaźnik interfejsu do wystąpienia dowolnego z typów Menedżera, który może być używany przez hosta do konfigurowania środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="2f651-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f651-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2f651-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f651-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2f651-105">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="2f651-106">podczas `IID` Typ Menedżera do zwrócenia.</span><span class="sxs-lookup"><span data-stu-id="2f651-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="2f651-107">`IID`Obsługiwane są następujące wartości.</span><span class="sxs-lookup"><span data-stu-id="2f651-107">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="2f651-108">IID_ICLRDebugManager: określa, że `ppObject` będzie typu [ICLRDebugManager](iclrdebugmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2f651-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="2f651-109">IID_ICLRErrorReportingManager: określa, że `ppObject` będzie typu [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2f651-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="2f651-110">IID_ICLRGCManager: określa, że `ppObject` będzie typu [ICLRGCManager](iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2f651-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="2f651-111">IID_ICLRHostProtectionManager: określa, że `ppObject` będzie typu [ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2f651-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="2f651-112">IID_ICLROnEventManager: określa, że `ppObject` będzie typu [ICLROnEventManager](iclroneventmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2f651-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="2f651-113">IID_ICLRPolicyManager: określa, że `ppObject` będzie typu [ICLRPolicyManager](iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2f651-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="2f651-114">IID_ICLRTaskManager: określa, że `ppObject` będzie typu [ICLRTaskManager](iclrtaskmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2f651-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="2f651-115">określoną Wskaźnik interfejsu do żądanego Menedżera lub wartość null, jeśli zażądano nieprawidłowego typu Menedżera.</span><span class="sxs-lookup"><span data-stu-id="2f651-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f651-116">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="2f651-116">Return Value</span></span>  
  
|<span data-ttu-id="2f651-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2f651-117">HRESULT</span></span>|<span data-ttu-id="2f651-118">Opis</span><span class="sxs-lookup"><span data-stu-id="2f651-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2f651-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f651-119">S_OK</span></span>|<span data-ttu-id="2f651-120">Metoda została pomyślnie zwrócona.</span><span class="sxs-lookup"><span data-stu-id="2f651-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="2f651-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2f651-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2f651-122">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="2f651-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2f651-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2f651-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2f651-124">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="2f651-124">The call timed out.</span></span>|  
|<span data-ttu-id="2f651-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2f651-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2f651-126">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="2f651-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2f651-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2f651-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2f651-128">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="2f651-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2f651-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2f651-129">E_FAIL</span></span>|<span data-ttu-id="2f651-130">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="2f651-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2f651-131">Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie.</span><span class="sxs-lookup"><span data-stu-id="2f651-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2f651-132">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2f651-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2f651-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="2f651-133">E_NOINTERFACE</span></span>|<span data-ttu-id="2f651-134">Typ interfejsu nie jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="2f651-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2f651-135">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2f651-135">Requirements</span></span>  

 <span data-ttu-id="2f651-136">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f651-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f651-137">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2f651-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2f651-138">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2f651-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f651-139">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f651-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f651-140">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2f651-140">See also</span></span>

- [<span data-ttu-id="2f651-141">ICLRControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2f651-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="2f651-142">IHostControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2f651-142">IHostControl Interface</span></span>](ihostcontrol-interface.md)
