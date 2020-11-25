---
title: ICLRPolicyManager::SetDefaultAction — Metoda
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
ms.openlocfilehash: 93070690ea6b30b22949953f1ed0b8c5b1e92764
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732485"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="cf95a-102">ICLRPolicyManager::SetDefaultAction — Metoda</span><span class="sxs-lookup"><span data-stu-id="cf95a-102">ICLRPolicyManager::SetDefaultAction Method</span></span>

<span data-ttu-id="cf95a-103">Określa akcję zasad, która ma być wykonywana przez środowisko uruchomieniowe języka wspólnego (CLR) w przypadku wystąpienia określonej operacji.</span><span class="sxs-lookup"><span data-stu-id="cf95a-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf95a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cf95a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf95a-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cf95a-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="cf95a-106">podczas Jedna z wartości [EClrOperation —](eclroperation-enumeration.md) , wskazująca na akcję, dla której ma zostać dostosowane zachowanie środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="cf95a-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="cf95a-107">podczas Jedna z wartości [EPolicyAction —](epolicyaction-enumeration.md) , wskazująca na akcję zasad, jakie powinien wykonać środowisko CLR, gdy `operation` wystąpi.</span><span class="sxs-lookup"><span data-stu-id="cf95a-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf95a-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="cf95a-108">Return Value</span></span>  
  
|<span data-ttu-id="cf95a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cf95a-109">HRESULT</span></span>|<span data-ttu-id="cf95a-110">Opis</span><span class="sxs-lookup"><span data-stu-id="cf95a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cf95a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cf95a-111">S_OK</span></span>|<span data-ttu-id="cf95a-112">`SetDefaultAction` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="cf95a-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="cf95a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cf95a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cf95a-114">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="cf95a-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cf95a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cf95a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cf95a-116">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="cf95a-116">The call timed out.</span></span>|  
|<span data-ttu-id="cf95a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cf95a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cf95a-118">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="cf95a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cf95a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cf95a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cf95a-120">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="cf95a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cf95a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cf95a-121">E_FAIL</span></span>|<span data-ttu-id="cf95a-122">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="cf95a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cf95a-123">Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie.</span><span class="sxs-lookup"><span data-stu-id="cf95a-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cf95a-124">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cf95a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cf95a-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="cf95a-125">E_INVALIDARG</span></span>|<span data-ttu-id="cf95a-126">`action` `operation` Dla lub podano nieprawidłową wartość dla elementu `operation` .</span><span class="sxs-lookup"><span data-stu-id="cf95a-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf95a-127">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cf95a-127">Remarks</span></span>  

 <span data-ttu-id="cf95a-128">Nie można określić wszystkich wartości akcji zasad jako domyślnego zachowania dla operacji CLR.</span><span class="sxs-lookup"><span data-stu-id="cf95a-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="cf95a-129">`SetDefaultAction` zazwyczaj może być używany tylko do eskalacji zachowania.</span><span class="sxs-lookup"><span data-stu-id="cf95a-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="cf95a-130">Na przykład host może określić, że przerwania wątku są włączane do przerwania wątku prosta, ale nie można określić przeciwieństwa.</span><span class="sxs-lookup"><span data-stu-id="cf95a-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="cf95a-131">W poniższej tabeli opisano prawidłowe `action` wartości dla każdej możliwej `operation` wartości.</span><span class="sxs-lookup"><span data-stu-id="cf95a-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="cf95a-132">Wartość dla `operation`</span><span class="sxs-lookup"><span data-stu-id="cf95a-132">Value for `operation`</span></span>|<span data-ttu-id="cf95a-133">Prawidłowe wartości dla `action`</span><span class="sxs-lookup"><span data-stu-id="cf95a-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="cf95a-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="cf95a-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="cf95a-135">- eAbortThread</span><span class="sxs-lookup"><span data-stu-id="cf95a-135">-   eAbortThread</span></span><br /><span data-ttu-id="cf95a-136">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="cf95a-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="cf95a-137">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="cf95a-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="cf95a-138">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="cf95a-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="cf95a-139">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-139">-   eExitProcess</span></span><br /><span data-ttu-id="cf95a-140">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="cf95a-141">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="cf95a-142">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="cf95a-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="cf95a-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="cf95a-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="cf95a-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="cf95a-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="cf95a-145">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="cf95a-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="cf95a-146">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="cf95a-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="cf95a-147">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="cf95a-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="cf95a-148">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-148">-   eExitProcess</span></span><br /><span data-ttu-id="cf95a-149">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="cf95a-150">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="cf95a-151">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="cf95a-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="cf95a-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="cf95a-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="cf95a-153">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="cf95a-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="cf95a-154">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="cf95a-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="cf95a-155">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-155">-   eExitProcess</span></span><br /><span data-ttu-id="cf95a-156">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="cf95a-157">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="cf95a-158">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="cf95a-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="cf95a-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="cf95a-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="cf95a-160">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="cf95a-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="cf95a-161">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-161">-   eExitProcess</span></span><br /><span data-ttu-id="cf95a-162">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="cf95a-163">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="cf95a-164">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="cf95a-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="cf95a-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="cf95a-165">OPR_ProcessExit</span></span>|<span data-ttu-id="cf95a-166">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-166">-   eExitProcess</span></span><br /><span data-ttu-id="cf95a-167">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="cf95a-168">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="cf95a-169">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="cf95a-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="cf95a-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="cf95a-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="cf95a-171">- eNoAction</span><span class="sxs-lookup"><span data-stu-id="cf95a-171">-   eNoAction</span></span><br /><span data-ttu-id="cf95a-172">- eAbortThread</span><span class="sxs-lookup"><span data-stu-id="cf95a-172">-   eAbortThread</span></span><br /><span data-ttu-id="cf95a-173">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="cf95a-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="cf95a-174">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="cf95a-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="cf95a-175">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="cf95a-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="cf95a-176">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-176">-   eExitProcess</span></span><br /><span data-ttu-id="cf95a-177">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="cf95a-178">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="cf95a-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="cf95a-179">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="cf95a-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cf95a-180">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cf95a-180">Requirements</span></span>  

 <span data-ttu-id="cf95a-181">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf95a-181">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf95a-182">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cf95a-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf95a-183">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cf95a-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf95a-184">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf95a-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf95a-185">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cf95a-185">See also</span></span>

- [<span data-ttu-id="cf95a-186">EClrOperation — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="cf95a-186">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="cf95a-187">EPolicyAction — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="cf95a-187">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="cf95a-188">ICLRPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="cf95a-188">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
