---
title: ICLRHostBindingPolicyManager::EvaluatePolicy — Metoda
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
ms.openlocfilehash: 9840217abdf8b3e1d0917b7447572b6860c181c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720311"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="50dde-102">ICLRHostBindingPolicyManager::EvaluatePolicy — Metoda</span><span class="sxs-lookup"><span data-stu-id="50dde-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>

<span data-ttu-id="50dde-103">Oblicza zasady powiązań w imieniu hosta.</span><span class="sxs-lookup"><span data-stu-id="50dde-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50dde-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="50dde-104">Syntax</span></span>  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50dde-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="50dde-105">Parameters</span></span>  

 `pwzReferenceIdentity`  
 <span data-ttu-id="50dde-106">podczas Odwołanie do zestawu przed oceną zasad.</span><span class="sxs-lookup"><span data-stu-id="50dde-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="50dde-107">podczas Wskaźnik do buforu, który zawiera dane zasad.</span><span class="sxs-lookup"><span data-stu-id="50dde-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="50dde-108">podczas Rozmiar `pbApplicationPolicy` buforu.</span><span class="sxs-lookup"><span data-stu-id="50dde-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="50dde-109">określoną Odwołanie do zestawu po dokonaniu oceny nowych danych zasad.</span><span class="sxs-lookup"><span data-stu-id="50dde-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="50dde-110">[in. out] Wskaźnik do rozmiaru buforu odwołań tożsamości zestawu po dokonaniu oceny nowych danych zasad.</span><span class="sxs-lookup"><span data-stu-id="50dde-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="50dde-111">określoną Wskaźnik do logicznej lub kombinacji wartości [EBindPolicyLevels —](ebindpolicylevels-enumeration.md) wskazujących, które zasady zostały zastosowane.</span><span class="sxs-lookup"><span data-stu-id="50dde-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50dde-112">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="50dde-112">Return Value</span></span>  
  
|<span data-ttu-id="50dde-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50dde-113">HRESULT</span></span>|<span data-ttu-id="50dde-114">Opis</span><span class="sxs-lookup"><span data-stu-id="50dde-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50dde-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="50dde-115">S_OK</span></span>|<span data-ttu-id="50dde-116">Ocena została zakończona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="50dde-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="50dde-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="50dde-117">E_INVALIDARG</span></span>|<span data-ttu-id="50dde-118">Albo `pwzReferenceIdentity` `pbApplicationPolicy` jest odwołaniem o wartości null.</span><span class="sxs-lookup"><span data-stu-id="50dde-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="50dde-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="50dde-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="50dde-120">`cbAppPolicySize` jest za mała.</span><span class="sxs-lookup"><span data-stu-id="50dde-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="50dde-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50dde-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50dde-122">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="50dde-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="50dde-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="50dde-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="50dde-124">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="50dde-124">The call timed out.</span></span>|  
|<span data-ttu-id="50dde-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="50dde-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="50dde-126">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="50dde-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="50dde-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="50dde-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="50dde-128">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="50dde-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="50dde-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50dde-129">E_FAIL</span></span>|<span data-ttu-id="50dde-130">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="50dde-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="50dde-131">Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie.</span><span class="sxs-lookup"><span data-stu-id="50dde-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="50dde-132">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="50dde-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50dde-133">Uwagi</span><span class="sxs-lookup"><span data-stu-id="50dde-133">Remarks</span></span>  

 <span data-ttu-id="50dde-134">`EvaluatePolicy`Metoda umożliwia hostowi wpływ na powiązania zasad w celu obsługi wymagań dotyczących wersji zestawu specyficznych dla hosta.</span><span class="sxs-lookup"><span data-stu-id="50dde-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="50dde-135">Sam aparat zasad pozostaje wewnątrz środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="50dde-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50dde-136">Wymagania</span><span class="sxs-lookup"><span data-stu-id="50dde-136">Requirements</span></span>  

 <span data-ttu-id="50dde-137">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50dde-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50dde-138">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="50dde-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50dde-139">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="50dde-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50dde-140">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50dde-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50dde-141">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="50dde-141">See also</span></span>

- [<span data-ttu-id="50dde-142">ICLRHostBindingPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="50dde-142">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
