---
title: ICLRPolicyManager::SetActionOnFailure — Metoda
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
ms.openlocfilehash: 8f44247ca7904a40f5ebc092d95c2e08b6048438
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725576"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="f1d92-102">ICLRPolicyManager::SetActionOnFailure — Metoda</span><span class="sxs-lookup"><span data-stu-id="f1d92-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>

<span data-ttu-id="f1d92-103">Określa akcję zasad, która ma być wykonywana przez środowisko uruchomieniowe języka wspólnego (CLR) w przypadku wystąpienia określonego błędu.</span><span class="sxs-lookup"><span data-stu-id="f1d92-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1d92-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f1d92-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1d92-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f1d92-105">Parameters</span></span>  

 `failure`  
 <span data-ttu-id="f1d92-106">podczas Jedna z wartości [EClrFailure —](eclrfailure-enumeration.md) , wskazująca typ błędu, dla którego należy podjąć działania.</span><span class="sxs-lookup"><span data-stu-id="f1d92-106">[in] One of the [EClrFailure](eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="f1d92-107">podczas Jedna z wartości [EPolicyAction —](epolicyaction-enumeration.md) , wskazująca akcję do wykonania w przypadku wystąpienia błędu.</span><span class="sxs-lookup"><span data-stu-id="f1d92-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="f1d92-108">Aby zapoznać się z listą obsługiwanych wartości, zobacz sekcję Uwagi.</span><span class="sxs-lookup"><span data-stu-id="f1d92-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1d92-109">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f1d92-109">Return Value</span></span>  
  
|<span data-ttu-id="f1d92-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f1d92-110">HRESULT</span></span>|<span data-ttu-id="f1d92-111">Opis</span><span class="sxs-lookup"><span data-stu-id="f1d92-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f1d92-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f1d92-112">S_OK</span></span>|<span data-ttu-id="f1d92-113">`SetActionOnFailure` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="f1d92-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="f1d92-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f1d92-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f1d92-115">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="f1d92-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f1d92-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f1d92-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f1d92-117">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="f1d92-117">The call timed out.</span></span>|  
|<span data-ttu-id="f1d92-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f1d92-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f1d92-119">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="f1d92-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f1d92-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f1d92-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f1d92-121">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="f1d92-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f1d92-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f1d92-122">E_FAIL</span></span>|<span data-ttu-id="f1d92-123">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="f1d92-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f1d92-124">Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie.</span><span class="sxs-lookup"><span data-stu-id="f1d92-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f1d92-125">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f1d92-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f1d92-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f1d92-126">E_INVALIDARG</span></span>|<span data-ttu-id="f1d92-127">Nie można ustawić akcji zasad dla określonej operacji lub określono nieprawidłową akcję zasad dla tej operacji.</span><span class="sxs-lookup"><span data-stu-id="f1d92-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1d92-128">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f1d92-128">Remarks</span></span>  

 <span data-ttu-id="f1d92-129">Domyślnie środowisko CLR zgłasza wyjątek, gdy nie może przydzielić zasobu, takiego jak pamięć.</span><span class="sxs-lookup"><span data-stu-id="f1d92-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="f1d92-130">`SetActionOnFailure` umożliwia hostowi przesłonięcie tego zachowania przez określenie akcji zasad, która ma zostać podjęta po awarii.</span><span class="sxs-lookup"><span data-stu-id="f1d92-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="f1d92-131">W poniższej tabeli przedstawiono kombinacje obsługiwanych wartości [EClrFailure —](eclrfailure-enumeration.md) i [EPolicyAction —](epolicyaction-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="f1d92-131">The following table shows the combinations of [EClrFailure](eclrfailure-enumeration.md) and [EPolicyAction](epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="f1d92-132">(Prefiks FAIL_ został pominięty z wartości [EClrFailure —](eclrfailure-enumeration.md) ).</span><span class="sxs-lookup"><span data-stu-id="f1d92-132">(The FAIL_ prefix is omitted from [EClrFailure](eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="f1d92-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="f1d92-133">NonCriticalResource</span></span>|<span data-ttu-id="f1d92-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="f1d92-134">CriticalResource</span></span>|<span data-ttu-id="f1d92-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="f1d92-135">FatalRuntime</span></span>|<span data-ttu-id="f1d92-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="f1d92-136">OrphanedLock</span></span>|<span data-ttu-id="f1d92-137">Witryna StackOverflow</span><span class="sxs-lookup"><span data-stu-id="f1d92-137">StackOverflow</span></span>|<span data-ttu-id="f1d92-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="f1d92-138">AccessViolation</span></span>|<span data-ttu-id="f1d92-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="f1d92-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="f1d92-140">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-140">X</span></span>|<span data-ttu-id="f1d92-141">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-141">X</span></span>||||<span data-ttu-id="f1d92-142">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="f1d92-142">N/A</span></span>||  
|<span data-ttu-id="f1d92-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="f1d92-143">eThrowException</span></span>|<span data-ttu-id="f1d92-144">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-144">X</span></span>|<span data-ttu-id="f1d92-145">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-145">X</span></span>||||<span data-ttu-id="f1d92-146">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="f1d92-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="f1d92-147">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-147">X</span></span>|<span data-ttu-id="f1d92-148">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-148">X</span></span>||||<span data-ttu-id="f1d92-149">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="f1d92-149">N/A</span></span>|<span data-ttu-id="f1d92-150">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="f1d92-151">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-151">X</span></span>|<span data-ttu-id="f1d92-152">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-152">X</span></span>||||<span data-ttu-id="f1d92-153">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="f1d92-153">N/A</span></span>|<span data-ttu-id="f1d92-154">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="f1d92-155">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-155">X</span></span>|<span data-ttu-id="f1d92-156">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-156">X</span></span>||<span data-ttu-id="f1d92-157">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-157">X</span></span>||<span data-ttu-id="f1d92-158">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="f1d92-158">N/A</span></span>|<span data-ttu-id="f1d92-159">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="f1d92-160">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-160">X</span></span>|<span data-ttu-id="f1d92-161">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-161">X</span></span>||<span data-ttu-id="f1d92-162">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-162">X</span></span>|<span data-ttu-id="f1d92-163">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-163">X</span></span>|<span data-ttu-id="f1d92-164">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="f1d92-164">N/A</span></span>|<span data-ttu-id="f1d92-165">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="f1d92-166">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-166">X</span></span>|<span data-ttu-id="f1d92-167">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-167">X</span></span>||<span data-ttu-id="f1d92-168">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-168">X</span></span>|<span data-ttu-id="f1d92-169">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-169">X</span></span>|<span data-ttu-id="f1d92-170">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="f1d92-170">N/A</span></span>|<span data-ttu-id="f1d92-171">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-171">X</span></span>|  
|<span data-ttu-id="f1d92-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="f1d92-172">eFastExitProcess</span></span>|<span data-ttu-id="f1d92-173">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-173">X</span></span>|<span data-ttu-id="f1d92-174">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-174">X</span></span>||<span data-ttu-id="f1d92-175">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-175">X</span></span>|<span data-ttu-id="f1d92-176">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-176">X</span></span>|<span data-ttu-id="f1d92-177">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="f1d92-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="f1d92-178">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-178">X</span></span>|<span data-ttu-id="f1d92-179">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-179">X</span></span>|<span data-ttu-id="f1d92-180">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-180">X</span></span>|<span data-ttu-id="f1d92-181">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-181">X</span></span>|<span data-ttu-id="f1d92-182">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-182">X</span></span>|<span data-ttu-id="f1d92-183">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="f1d92-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="f1d92-184">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-184">X</span></span>|<span data-ttu-id="f1d92-185">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-185">X</span></span>|<span data-ttu-id="f1d92-186">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-186">X</span></span>|<span data-ttu-id="f1d92-187">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-187">X</span></span>|<span data-ttu-id="f1d92-188">X</span><span class="sxs-lookup"><span data-stu-id="f1d92-188">X</span></span>|<span data-ttu-id="f1d92-189">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="f1d92-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="f1d92-190">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f1d92-190">Requirements</span></span>  

 <span data-ttu-id="f1d92-191">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1d92-191">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1d92-192">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f1d92-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f1d92-193">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f1d92-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1d92-194">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1d92-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d92-195">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f1d92-195">See also</span></span>

- [<span data-ttu-id="f1d92-196">EClrFailure — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="f1d92-196">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="f1d92-197">EPolicyAction — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="f1d92-197">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="f1d92-198">ICLRControl — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f1d92-198">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="f1d92-199">ICLRPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f1d92-199">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
