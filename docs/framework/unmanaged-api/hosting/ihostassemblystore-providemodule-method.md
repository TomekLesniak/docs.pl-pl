---
title: IHostAssemblyStore::ProvideModule — Metoda
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
ms.openlocfilehash: 35805d277774e1de03bb7dee1740a2e1305a97c9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732999"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="8fae1-102">IHostAssemblyStore::ProvideModule — Metoda</span><span class="sxs-lookup"><span data-stu-id="8fae1-102">IHostAssemblyStore::ProvideModule Method</span></span>

<span data-ttu-id="8fae1-103">Rozpoznaje moduł wewnątrz zestawu lub połączony (ale nie osadzony) plik zasobów.</span><span class="sxs-lookup"><span data-stu-id="8fae1-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fae1-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="8fae1-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fae1-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="8fae1-105">Parameters</span></span>  

 `pBindInfo`  
 <span data-ttu-id="8fae1-106">podczas Wskaźnik do wystąpienia [ModuleBindInfo —](modulebindinfo-structure.md) , który opisuje żądany moduł <xref:System.AppDomain> , zestaw i nazwę modułu.</span><span class="sxs-lookup"><span data-stu-id="8fae1-106">[in] A pointer to a [ModuleBindInfo](modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="8fae1-107">określoną Wskaźnik do unikatowego identyfikatora `IStream` zawierającego załadowany moduł.</span><span class="sxs-lookup"><span data-stu-id="8fae1-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="8fae1-108">określoną Wskaźnik do adresu `IStream` obiektu, który zawiera obraz przenośnego pliku wykonywalnego (PE), który ma zostać załadowany lub ma wartość null, jeśli nie można znaleźć modułu.</span><span class="sxs-lookup"><span data-stu-id="8fae1-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="8fae1-109">określoną Wskaźnik do adresu `IStream` obiektu, który zawiera informacje o debugowaniu programu (PDB) dla żądanego modułu, lub wartość null, jeśli nie można znaleźć pliku. pdb.</span><span class="sxs-lookup"><span data-stu-id="8fae1-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8fae1-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="8fae1-110">Return Value</span></span>  
  
|<span data-ttu-id="8fae1-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8fae1-111">HRESULT</span></span>|<span data-ttu-id="8fae1-112">Opis</span><span class="sxs-lookup"><span data-stu-id="8fae1-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8fae1-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8fae1-113">S_OK</span></span>|<span data-ttu-id="8fae1-114">`ProvideModule` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="8fae1-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="8fae1-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8fae1-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8fae1-116">Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="8fae1-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8fae1-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8fae1-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8fae1-118">Upłynął limit czasu połączenia.</span><span class="sxs-lookup"><span data-stu-id="8fae1-118">The call timed out.</span></span>|  
|<span data-ttu-id="8fae1-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8fae1-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8fae1-120">Obiekt wywołujący nie jest właocicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="8fae1-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8fae1-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8fae1-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8fae1-122">Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.</span><span class="sxs-lookup"><span data-stu-id="8fae1-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8fae1-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8fae1-123">E_FAIL</span></span>|<span data-ttu-id="8fae1-124">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="8fae1-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8fae1-125">Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie.</span><span class="sxs-lookup"><span data-stu-id="8fae1-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8fae1-126">Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8fae1-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8fae1-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="8fae1-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="8fae1-128">Nie można zlokalizować żądanego zestawu lub połączonego zasobu.</span><span class="sxs-lookup"><span data-stu-id="8fae1-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="8fae1-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="8fae1-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="8fae1-130">`pdwModuleId` nie jest wystarczająco duży, aby można było zawierać identyfikator, który chce zwrócić host.</span><span class="sxs-lookup"><span data-stu-id="8fae1-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fae1-131">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8fae1-131">Remarks</span></span>  

 <span data-ttu-id="8fae1-132">Zwracana wartość tożsamości `pdwModuleId` jest określana przez hosta.</span><span class="sxs-lookup"><span data-stu-id="8fae1-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="8fae1-133">Identyfikatory muszą być unikatowe w okresie istnienia procesu.</span><span class="sxs-lookup"><span data-stu-id="8fae1-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="8fae1-134">Środowisko CLR używa tej wartości jako unikatowego identyfikatora skojarzonego strumienia.</span><span class="sxs-lookup"><span data-stu-id="8fae1-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="8fae1-135">Sprawdza każdą wartość dla wartości `pAssemblyId` zwracanych przez wywołania do [ProvideAssembly —](ihostassemblystore-provideassembly-method.md) i wartości `pdwModuleId` zwracanych przez inne wywołania do `ProvideModule` .</span><span class="sxs-lookup"><span data-stu-id="8fae1-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="8fae1-136">Jeśli host zwraca tę samą wartość identyfikatora dla innego `IStream` , środowisko CLR sprawdza, czy zawartość tego strumienia została już zamapowana.</span><span class="sxs-lookup"><span data-stu-id="8fae1-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="8fae1-137">Jeśli tak, środowisko CLR ładuje istniejącą kopię obrazu zamiast mapowania nowej.</span><span class="sxs-lookup"><span data-stu-id="8fae1-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="8fae1-138">W związku z tym, identyfikator nie może również nakładać się na identyfikatory zestawu zwrócone z `ProvideAssembly` .</span><span class="sxs-lookup"><span data-stu-id="8fae1-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fae1-139">Wymagania</span><span class="sxs-lookup"><span data-stu-id="8fae1-139">Requirements</span></span>  

 <span data-ttu-id="8fae1-140">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fae1-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fae1-141">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8fae1-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8fae1-142">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8fae1-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8fae1-143">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fae1-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fae1-144">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8fae1-144">See also</span></span>

- [<span data-ttu-id="8fae1-145">ICLRAssemblyReferenceList — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8fae1-145">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="8fae1-146">IHostAssemblyManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8fae1-146">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="8fae1-147">IHostAssemblyStore — Interfejs</span><span class="sxs-lookup"><span data-stu-id="8fae1-147">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
