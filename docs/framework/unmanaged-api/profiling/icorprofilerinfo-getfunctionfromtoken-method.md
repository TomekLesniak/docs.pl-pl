---
title: ICorProfilerInfo::GetFunctionFromToken — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type:
- apiref
ms.openlocfilehash: 9c7f01d2e462ad1cb0532be6f369c3118a4deb6a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722495"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="83e6e-102">ICorProfilerInfo::GetFunctionFromToken — Metoda</span><span class="sxs-lookup"><span data-stu-id="83e6e-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>

<span data-ttu-id="83e6e-103">Pobiera identyfikator funkcji.</span><span class="sxs-lookup"><span data-stu-id="83e6e-103">Gets the ID of a function.</span></span> <span data-ttu-id="83e6e-104">Ta metoda jest przestarzała w .NET Framework w wersji 2,0.</span><span class="sxs-lookup"><span data-stu-id="83e6e-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="83e6e-105">Zamiast tego użyj metody [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs —](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="83e6e-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83e6e-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="83e6e-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="83e6e-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="83e6e-107">Remarks</span></span>  

 <span data-ttu-id="83e6e-108">`GetFunctionFromToken`Metoda nie będzie działać w przypadku funkcji ogólnych lub funkcji w typach ogólnych; jest ona już przestarzała.</span><span class="sxs-lookup"><span data-stu-id="83e6e-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="83e6e-109">Użyj `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` dla wszystkich funkcji.</span><span class="sxs-lookup"><span data-stu-id="83e6e-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83e6e-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="83e6e-110">Requirements</span></span>  

 <span data-ttu-id="83e6e-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83e6e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83e6e-112">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="83e6e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="83e6e-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="83e6e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83e6e-114">**.NET Framework wersje:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="83e6e-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e6e-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="83e6e-115">See also</span></span>

- [<span data-ttu-id="83e6e-116">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="83e6e-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
