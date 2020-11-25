---
title: ICorProfilerInfo3::GetAppDomainsContainingModule — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type:
- apiref
ms.openlocfilehash: 5cc3436716bcfc2ed0f9fd7ff7982bac7a48de9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731205"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="65d1d-102">ICorProfilerInfo3::GetAppDomainsContainingModule — Metoda</span><span class="sxs-lookup"><span data-stu-id="65d1d-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>

<span data-ttu-id="65d1d-103">Pobiera identyfikatory domen aplikacji, w których dany moduł został załadowany.</span><span class="sxs-lookup"><span data-stu-id="65d1d-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65d1d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="65d1d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65d1d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="65d1d-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="65d1d-106">podczas Identyfikator załadowanego modułu.</span><span class="sxs-lookup"><span data-stu-id="65d1d-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="65d1d-107">podczas Rozmiar `appDomainIds` tablicy.</span><span class="sxs-lookup"><span data-stu-id="65d1d-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="65d1d-108">określoną Wskaźnik do łącznej liczby zwróconych elementów.</span><span class="sxs-lookup"><span data-stu-id="65d1d-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="65d1d-109">określoną Tablica wartości identyfikatora domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="65d1d-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65d1d-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="65d1d-110">Remarks</span></span>  

 <span data-ttu-id="65d1d-111">Metoda używa buforów przyznanych przez wywołującego.</span><span class="sxs-lookup"><span data-stu-id="65d1d-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65d1d-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="65d1d-112">Requirements</span></span>  

 <span data-ttu-id="65d1d-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65d1d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65d1d-114">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="65d1d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="65d1d-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="65d1d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65d1d-116">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65d1d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65d1d-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="65d1d-117">See also</span></span>

- [<span data-ttu-id="65d1d-118">ICorProfilerFunctionEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="65d1d-118">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="65d1d-119">ICorProfilerInfo3 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="65d1d-119">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="65d1d-120">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="65d1d-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="65d1d-121">Profilowanie</span><span class="sxs-lookup"><span data-stu-id="65d1d-121">Profiling</span></span>](index.md)
