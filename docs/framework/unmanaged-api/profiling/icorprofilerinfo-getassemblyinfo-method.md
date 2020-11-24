---
title: ICorProfilerInfo::GetAssemblyInfo — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAssemblyInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyInfo Method
helpviewer_keywords:
- GetAssemblyInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetAssemblyInfo method [.NET Framework profiling]
ms.assetid: 7a3c97c3-1e31-47b1-bf23-386785c509c4
topic_type:
- apiref
ms.openlocfilehash: ff81da15b17ab0a7fbe62b08e358f65eed3edb71
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680279"
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a><span data-ttu-id="2973e-102">ICorProfilerInfo::GetAssemblyInfo — Metoda</span><span class="sxs-lookup"><span data-stu-id="2973e-102">ICorProfilerInfo::GetAssemblyInfo Method</span></span>

<span data-ttu-id="2973e-103">Akceptuje identyfikator zestawu i zwraca nazwę zestawu oraz identyfikator modułu manifestu.</span><span class="sxs-lookup"><span data-stu-id="2973e-103">Accepts an assembly ID, and returns the assembly's name and the ID of its manifest module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2973e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2973e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyInfo(  
    [in]  AssemblyID  assemblyId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] AppDomainID *pAppDomainId,  
    [out] ModuleID    *pModuleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2973e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2973e-105">Parameters</span></span>  

 `assemblyId`  
 <span data-ttu-id="2973e-106">podczas Identyfikator zestawu.</span><span class="sxs-lookup"><span data-stu-id="2973e-106">[in] The identifier of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="2973e-107">podczas Długość, w znakach, z `szName` .</span><span class="sxs-lookup"><span data-stu-id="2973e-107">[in] The length, in characters, of `szName`.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2973e-108">określoną Wskaźnik do łącznej długości znaku nazwy zestawu.</span><span class="sxs-lookup"><span data-stu-id="2973e-108">[out] A pointer to the total character length of the assembly's name.</span></span>  
  
 `szName`  
 <span data-ttu-id="2973e-109">określoną Bufor znaków udostępniany przez obiekt wywołujący.</span><span class="sxs-lookup"><span data-stu-id="2973e-109">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="2973e-110">Gdy funkcja zwraca, będzie zawierać nazwę zestawu.</span><span class="sxs-lookup"><span data-stu-id="2973e-110">When the function returns, it will contain the assembly's name.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="2973e-111">określoną Wskaźnik do identyfikatora domeny aplikacji, który zawiera zestaw.</span><span class="sxs-lookup"><span data-stu-id="2973e-111">[out] A pointer to the ID of the application domain that contains the assembly.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="2973e-112">określoną Wskaźnik do identyfikatora modułu manifestu zestawu.</span><span class="sxs-lookup"><span data-stu-id="2973e-112">[out] A pointer to the ID of the assembly's manifest module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2973e-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2973e-113">Remarks</span></span>  

 <span data-ttu-id="2973e-114">Po powrocie tej metody należy sprawdzić, czy `szName` bufor jest wystarczająco duży, aby pomieścić pełną nazwę zestawu.</span><span class="sxs-lookup"><span data-stu-id="2973e-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the assembly.</span></span> <span data-ttu-id="2973e-115">W tym celu należy porównać wartość wskazującą wartość `pcchName` `cchName` parametru.</span><span class="sxs-lookup"><span data-stu-id="2973e-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="2973e-116">Jeśli `pcchName` wskazuje wartość, która jest większa niż `cchName` , Przydziel większy `szName` bufor, zaktualizuj `cchName` przy użyciu nowego, większego rozmiaru i ponownie wywołaj `GetAssemblyInfo` .</span><span class="sxs-lookup"><span data-stu-id="2973e-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAssemblyInfo` again.</span></span>  
  
 <span data-ttu-id="2973e-117">Alternatywnie, można najpierw wywołać `GetAssemblyInfo` z buforem o zerowej długości, `szName` Aby uzyskać prawidłowy rozmiar buforu.</span><span class="sxs-lookup"><span data-stu-id="2973e-117">Alternatively, you can first call `GetAssemblyInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="2973e-118">Następnie można dostosować rozmiar buforu na podstawie wartości zwróconej w `pcchName` i `GetAssemblyInfo` ponownie wywołać.</span><span class="sxs-lookup"><span data-stu-id="2973e-118">You can then adjust the buffer size based on the value returned in `pcchName` and call `GetAssemblyInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2973e-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2973e-119">Requirements</span></span>  

 <span data-ttu-id="2973e-120">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2973e-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2973e-121">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="2973e-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2973e-122">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2973e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2973e-123">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2973e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2973e-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2973e-124">See also</span></span>

- [<span data-ttu-id="2973e-125">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2973e-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="2973e-126">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="2973e-126">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="2973e-127">Profilowanie</span><span class="sxs-lookup"><span data-stu-id="2973e-127">Profiling</span></span>](index.md)
