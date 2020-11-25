---
title: ICLRPolicyManager::SetActionOnTimeout — Metoda
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
ms.openlocfilehash: 3ddd78ea35d5709abb30af085b2212a09b28c2ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725563"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="63ded-102">ICLRPolicyManager::SetActionOnTimeout — Metoda</span><span class="sxs-lookup"><span data-stu-id="63ded-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>

<span data-ttu-id="63ded-103">Określa akcję zasad, która ma być wykonywana przez środowisko uruchomieniowe języka wspólnego (CLR), gdy określona operacja przeprowadzi limit czasu.</span><span class="sxs-lookup"><span data-stu-id="63ded-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ded-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="63ded-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63ded-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="63ded-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="63ded-106">podczas Jedna z wartości [EClrOperation —](eclroperation-enumeration.md) , wskazująca na operację, dla której ma zostać określona akcja limitu czasu.</span><span class="sxs-lookup"><span data-stu-id="63ded-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="63ded-107">Obsługiwane są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="63ded-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="63ded-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="63ded-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="63ded-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="63ded-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="63ded-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="63ded-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="63ded-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="63ded-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="63ded-112">podczas Jedna z wartości [EPolicyAction —](epolicyaction-enumeration.md) , wskazująca akcję zasad, która ma zostać podjęta po przełączeniu operacji.</span><span class="sxs-lookup"><span data-stu-id="63ded-112">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63ded-113">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="63ded-113">Return Value</span></span>  
  
|<span data-ttu-id="63ded-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63ded-114">HRESULT</span></span>|<span data-ttu-id="63ded-115">Opis</span><span class="sxs-lookup"><span data-stu-id="63ded-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63ded-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="63ded-116">S_OK</span></span>|<span data-ttu-id="63ded-117">`SetActionOnTimeout` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="63ded-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="63ded-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="63ded-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="63ded-119">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="63ded-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="63ded-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="63ded-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="63ded-121">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="63ded-121">The call timed out.</span></span>|  
|<span data-ttu-id="63ded-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="63ded-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="63ded-123">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="63ded-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="63ded-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="63ded-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="63ded-125">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="63ded-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="63ded-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="63ded-126">E_FAIL</span></span>|<span data-ttu-id="63ded-127">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="63ded-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="63ded-128">Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie.</span><span class="sxs-lookup"><span data-stu-id="63ded-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="63ded-129">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="63ded-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="63ded-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="63ded-130">E_INVALIDARG</span></span>|<span data-ttu-id="63ded-131">Nie można ustawić limitu czasu dla określonego elementu `operation` lub podano nieprawidłową wartość dla elementu `operation` .</span><span class="sxs-lookup"><span data-stu-id="63ded-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63ded-132">Uwagi</span><span class="sxs-lookup"><span data-stu-id="63ded-132">Remarks</span></span>  

 <span data-ttu-id="63ded-133">Wartość limitu czasu może być domyślnym limitem czasu ustawionym przez środowisko CLR lub wartość określoną przez hosta w wywołaniu metody [ICLRPolicyManager:: setTimeout](iclrpolicymanager-settimeout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="63ded-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="63ded-134">Nie wszystkie wartości akcji zasad można określić jako zachowanie limitu czasu dla operacji CLR.</span><span class="sxs-lookup"><span data-stu-id="63ded-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="63ded-135">`SetActionOnTimeout` jest zazwyczaj używany tylko w celu eskalacji zachowań.</span><span class="sxs-lookup"><span data-stu-id="63ded-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="63ded-136">Na przykład host może określić, że przerwania wątku są włączane do przerwania wątku prosta, ale nie można określić przeciwieństwa.</span><span class="sxs-lookup"><span data-stu-id="63ded-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="63ded-137">W poniższej tabeli opisano prawidłowe `action` wartości prawidłowych wartości `operation` .</span><span class="sxs-lookup"><span data-stu-id="63ded-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="63ded-138">Wartość dla `operation`</span><span class="sxs-lookup"><span data-stu-id="63ded-138">Value for `operation`</span></span>|<span data-ttu-id="63ded-139">Prawidłowe wartości dla `action`</span><span class="sxs-lookup"><span data-stu-id="63ded-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="63ded-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="63ded-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="63ded-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="63ded-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="63ded-142">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="63ded-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="63ded-143">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="63ded-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="63ded-144">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="63ded-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="63ded-145">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="63ded-145">-   eExitProcess</span></span><br /><span data-ttu-id="63ded-146">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="63ded-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="63ded-147">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="63ded-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="63ded-148">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="63ded-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="63ded-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="63ded-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="63ded-150">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="63ded-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="63ded-151">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="63ded-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="63ded-152">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="63ded-152">-   eExitProcess</span></span><br /><span data-ttu-id="63ded-153">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="63ded-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="63ded-154">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="63ded-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="63ded-155">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="63ded-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="63ded-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="63ded-156">OPR_ProcessExit</span></span>|<span data-ttu-id="63ded-157">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="63ded-157">-   eExitProcess</span></span><br /><span data-ttu-id="63ded-158">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="63ded-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="63ded-159">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="63ded-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="63ded-160">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="63ded-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63ded-161">Wymagania</span><span class="sxs-lookup"><span data-stu-id="63ded-161">Requirements</span></span>  

 <span data-ttu-id="63ded-162">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63ded-162">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63ded-163">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="63ded-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63ded-164">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="63ded-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63ded-165">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63ded-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ded-166">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="63ded-166">See also</span></span>

- [<span data-ttu-id="63ded-167">EClrOperation — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="63ded-167">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="63ded-168">EPolicyAction — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="63ded-168">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="63ded-169">ICLRControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="63ded-169">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="63ded-170">ICLRPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="63ded-170">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
