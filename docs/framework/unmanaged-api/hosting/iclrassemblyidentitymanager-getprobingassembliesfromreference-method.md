---
title: ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference — Metoda
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
ms.openlocfilehash: 263058131e63205aa37f81847ed647944fef7540
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731400"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="3d75c-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference — Metoda</span><span class="sxs-lookup"><span data-stu-id="3d75c-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>

<span data-ttu-id="3d75c-103">Pobiera moduł wyliczający [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) dla tożsamości zestawu, do których odwołuje się zestaw o określonym typie tożsamości.</span><span class="sxs-lookup"><span data-stu-id="3d75c-103">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d75c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="3d75c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d75c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="3d75c-105">Parameters</span></span>  

 `dwMachineType`  
 <span data-ttu-id="3d75c-106">podczas Prawidłowa wartość określająca architekturę procesora, zgodnie z definicją w WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="3d75c-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3d75c-107">podczas Udostępniane do przyszłej rozszerzalności.</span><span class="sxs-lookup"><span data-stu-id="3d75c-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="3d75c-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT jest jedyną wartością, którą obsługuje bieżąca wersja środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="3d75c-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="3d75c-109">podczas Nieprzezroczysta tożsamość powiązania zestawu, zazwyczaj zwracana z wywołania metody [ICLRAssemblyIdentityManager:: GetBindingIdentityFromFile —](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) lub [ICLRAssemblyIdentityManager:: GetBindingIdentityFromStream —](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3d75c-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="3d75c-110">określoną Wskaźnik interfejsu do `ICLRProbingAssemblyEnum` modułu wyliczającego, który zawiera odwołania do zestawów, do których odwołuje się zestaw identyfikowany przez `pwzReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="3d75c-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d75c-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="3d75c-111">Return Value</span></span>  
  
|<span data-ttu-id="3d75c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3d75c-112">HRESULT</span></span>|<span data-ttu-id="3d75c-113">Opis</span><span class="sxs-lookup"><span data-stu-id="3d75c-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d75c-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3d75c-114">S_OK</span></span>|<span data-ttu-id="3d75c-115">Metoda została pomyślnie zwrócona.</span><span class="sxs-lookup"><span data-stu-id="3d75c-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="3d75c-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3d75c-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3d75c-117">Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="3d75c-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3d75c-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3d75c-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3d75c-119">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="3d75c-119">The call timed out.</span></span>|  
|<span data-ttu-id="3d75c-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3d75c-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3d75c-121">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="3d75c-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3d75c-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3d75c-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3d75c-123">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="3d75c-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3d75c-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3d75c-124">E_FAIL</span></span>|<span data-ttu-id="3d75c-125">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="3d75c-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3d75c-126">Jeśli metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="3d75c-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3d75c-127">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3d75c-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d75c-128">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3d75c-128">Requirements</span></span>  

 <span data-ttu-id="3d75c-129">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d75c-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d75c-130">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3d75c-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d75c-131">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3d75c-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d75c-132">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d75c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d75c-133">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3d75c-133">See also</span></span>

- [<span data-ttu-id="3d75c-134">ICLRAssemblyIdentityManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3d75c-134">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="3d75c-135">ICLRAssemblyReferenceList — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3d75c-135">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="3d75c-136">ICLRProbingAssemblyEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="3d75c-136">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
