---
title: ICorProfilerInfo::GetModuleInfo — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleInfo
helpviewer_keywords:
- GetModuleInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleInfo method [.NET Framework profiling]
ms.assetid: 5a90d16f-7929-4987-8f83-a631becf564d
topic_type:
- apiref
ms.openlocfilehash: 863fa1bf50830bb46e5c2939c99fe1e15897ac3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724133"
---
# <a name="icorprofilerinfogetmoduleinfo-method"></a><span data-ttu-id="c4727-102">ICorProfilerInfo::GetModuleInfo — Metoda</span><span class="sxs-lookup"><span data-stu-id="c4727-102">ICorProfilerInfo::GetModuleInfo Method</span></span>

<span data-ttu-id="c4727-103">Podanym IDENTYFIKATORem modułu zwraca nazwę pliku modułu i identyfikator zestawu nadrzędnego modułu.</span><span class="sxs-lookup"><span data-stu-id="c4727-103">Given a module ID, returns the file name of the module and the ID of the module's parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4727-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c4727-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleInfo(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4727-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c4727-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="c4727-106">podczas Identyfikator modułu, dla którego będą pobierane informacje.</span><span class="sxs-lookup"><span data-stu-id="c4727-106">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="c4727-107">określoną Adres podstawowy, z którego moduł jest załadowany.</span><span class="sxs-lookup"><span data-stu-id="c4727-107">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c4727-108">podczas Długość (w znakach) `szName` buforu powrotu.</span><span class="sxs-lookup"><span data-stu-id="c4727-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c4727-109">określoną Wskaźnik do łącznej długości znaku nazwy pliku modułu, który jest zwracany.</span><span class="sxs-lookup"><span data-stu-id="c4727-109">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="c4727-110">określoną Bufor znaków udostępniany przez obiekt wywołujący.</span><span class="sxs-lookup"><span data-stu-id="c4727-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="c4727-111">Gdy metoda zwraca, ten bufor zawiera nazwę pliku modułu.</span><span class="sxs-lookup"><span data-stu-id="c4727-111">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="c4727-112">określoną Wskaźnik do identyfikatora zestawu nadrzędnego modułu.</span><span class="sxs-lookup"><span data-stu-id="c4727-112">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4727-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c4727-113">Remarks</span></span>  

 <span data-ttu-id="c4727-114">Dla modułów dynamicznych `szName` parametr jest pustym ciągiem, a adres podstawowy to 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="c4727-114">For dynamic modules, the `szName` parameter is an empty string, and the base address is 0 (zero).</span></span>  
  
 <span data-ttu-id="c4727-115">Mimo że `GetModuleInfo` Metoda może być wywoływana, gdy tylko identyfikator modułu już istnieje, identyfikator zestawu nadrzędnego nie będzie dostępny do momentu otrzymania przez profiler wywołania zwrotnego [ICorProfilerCallback:: ModuleAttachedToAssembly —](icorprofilercallback-moduleattachedtoassembly-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c4727-115">Although the `GetModuleInfo` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="c4727-116">Gdy `GetModuleInfo` zwraca, należy sprawdzić, czy `szName` bufor jest wystarczająco duży, aby można było zawierać pełną nazwę pliku modułu.</span><span class="sxs-lookup"><span data-stu-id="c4727-116">When `GetModuleInfo` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="c4727-117">W tym celu należy porównać wartość wskazującą wartość `pcchName` `cchName` parametru.</span><span class="sxs-lookup"><span data-stu-id="c4727-117">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="c4727-118">Jeśli `pcchName` wskazuje wartość, która jest większa niż `cchName` , Przydziel większy `szName` bufor, zaktualizuj `cchName` przy użyciu nowego, większego rozmiaru i ponownie wywołaj `GetModuleInfo` .</span><span class="sxs-lookup"><span data-stu-id="c4727-118">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo` again.</span></span>  
  
 <span data-ttu-id="c4727-119">Alternatywnie, można najpierw wywołać `GetModuleInfo` z buforem o zerowej długości, `szName` Aby uzyskać prawidłowy rozmiar buforu.</span><span class="sxs-lookup"><span data-stu-id="c4727-119">Alternatively, you can first call `GetModuleInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="c4727-120">Następnie można ustawić rozmiar buforu na wartość zwracaną w `pcchName` i `GetModuleInfo` ponownie wywołać.</span><span class="sxs-lookup"><span data-stu-id="c4727-120">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4727-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c4727-121">Requirements</span></span>  

 <span data-ttu-id="c4727-122">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4727-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4727-123">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="c4727-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c4727-124">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c4727-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4727-125">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4727-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4727-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c4727-126">See also</span></span>

- [<span data-ttu-id="c4727-127">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c4727-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="c4727-128">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="c4727-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="c4727-129">Profilowanie</span><span class="sxs-lookup"><span data-stu-id="c4727-129">Profiling</span></span>](index.md)
- [<span data-ttu-id="c4727-130">GetModuleInfo2, metoda</span><span class="sxs-lookup"><span data-stu-id="c4727-130">GetModuleInfo2 Method</span></span>](icorprofilerinfo3-getmoduleinfo2-method.md)
