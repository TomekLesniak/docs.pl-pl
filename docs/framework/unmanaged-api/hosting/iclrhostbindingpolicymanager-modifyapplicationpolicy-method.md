---
title: ICLRHostBindingPolicyManager::ModifyApplicationPolicy — Metoda
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
ms.openlocfilehash: 8da9c9fea5cf5b3a27eeb9d0222f0845c832b7da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714201"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="d51d6-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy — Metoda</span><span class="sxs-lookup"><span data-stu-id="d51d6-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>

<span data-ttu-id="d51d6-103">Modyfikuje zasady powiązań dla określonego zestawu i tworzy nową wersję zasad.</span><span class="sxs-lookup"><span data-stu-id="d51d6-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d51d6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d51d6-104">Syntax</span></span>  
  
```cpp  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d51d6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d51d6-105">Parameters</span></span>  

 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="d51d6-106">podczas Tożsamość zestawu do zmodyfikowania.</span><span class="sxs-lookup"><span data-stu-id="d51d6-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="d51d6-107">podczas Nowa tożsamość zmodyfikowanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="d51d6-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="d51d6-108">podczas Wskaźnik do buforu, który zawiera dane zasad powiązań dla zestawu do zmodyfikowania.</span><span class="sxs-lookup"><span data-stu-id="d51d6-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="d51d6-109">podczas Rozmiar zasad powiązania, które mają zostać zastąpione.</span><span class="sxs-lookup"><span data-stu-id="d51d6-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="d51d6-110">podczas Logiczne lub kombinacja wartości [EHostBindingPolicyModifyFlags —](ehostbindingpolicymodifyflags-enumeration.md) wskazujących na kontrolę przekierowania.</span><span class="sxs-lookup"><span data-stu-id="d51d6-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="d51d6-111">określoną Wskaźnik do buforu, który zawiera nowe dane zasad powiązań.</span><span class="sxs-lookup"><span data-stu-id="d51d6-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="d51d6-112">[in. out] Wskaźnik do rozmiaru nowego buforu zasad powiązania.</span><span class="sxs-lookup"><span data-stu-id="d51d6-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d51d6-113">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="d51d6-113">Return Value</span></span>  
  
|<span data-ttu-id="d51d6-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d51d6-114">HRESULT</span></span>|<span data-ttu-id="d51d6-115">Opis</span><span class="sxs-lookup"><span data-stu-id="d51d6-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d51d6-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="d51d6-116">S_OK</span></span>|<span data-ttu-id="d51d6-117">Zasady zostały zmodyfikowane pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="d51d6-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="d51d6-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d51d6-118">E_INVALIDARG</span></span>|<span data-ttu-id="d51d6-119">`pwzSourceAssemblyIdentity` lub `pwzTargetAssemblyIdentity` było odwołaniem o wartości null.</span><span class="sxs-lookup"><span data-stu-id="d51d6-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="d51d6-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="d51d6-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="d51d6-121">`pbNewApplicationPolicy` jest za mała.</span><span class="sxs-lookup"><span data-stu-id="d51d6-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="d51d6-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d51d6-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d51d6-123">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="d51d6-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d51d6-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d51d6-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d51d6-125">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="d51d6-125">The call timed out.</span></span>|  
|<span data-ttu-id="d51d6-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d51d6-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d51d6-127">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="d51d6-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d51d6-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d51d6-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d51d6-129">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="d51d6-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d51d6-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d51d6-130">E_FAIL</span></span>|<span data-ttu-id="d51d6-131">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="d51d6-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d51d6-132">Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie.</span><span class="sxs-lookup"><span data-stu-id="d51d6-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d51d6-133">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d51d6-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d51d6-134">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d51d6-134">Remarks</span></span>  

 <span data-ttu-id="d51d6-135">`ModifyApplicationPolicy`Metodę można wywołać dwukrotnie.</span><span class="sxs-lookup"><span data-stu-id="d51d6-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="d51d6-136">Pierwsze wywołanie powinno podawać wartość null dla `pbNewApplicationPolicy` parametru.</span><span class="sxs-lookup"><span data-stu-id="d51d6-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="d51d6-137">To wywołanie zwróci wartość wymaganą dla parametru `pcbNewAppPolicySize` .</span><span class="sxs-lookup"><span data-stu-id="d51d6-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="d51d6-138">Drugie wywołanie powinno dostarczyć tę wartość dla `pcbNewAppPolicySize` i wskazać bufor tego rozmiaru dla `pbNewApplicationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="d51d6-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d51d6-139">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d51d6-139">Requirements</span></span>  

 <span data-ttu-id="d51d6-140">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d51d6-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d51d6-141">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d51d6-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d51d6-142">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d51d6-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d51d6-143">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d51d6-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d51d6-144">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d51d6-144">See also</span></span>

- [<span data-ttu-id="d51d6-145">ICLRHostBindingPolicyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d51d6-145">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
