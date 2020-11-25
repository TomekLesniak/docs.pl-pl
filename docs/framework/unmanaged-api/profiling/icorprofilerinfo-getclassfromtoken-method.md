---
title: ICorProfilerInfo::GetClassFromToken — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 7d9fe7d6d5c5af32be22ba19b52e7d40033a6eb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706752"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="489f8-102">ICorProfilerInfo::GetClassFromToken — Metoda</span><span class="sxs-lookup"><span data-stu-id="489f8-102">ICorProfilerInfo::GetClassFromToken Method</span></span>

<span data-ttu-id="489f8-103">Pobiera identyfikator klasy, z uwzględnieniem tokenu metadanych.</span><span class="sxs-lookup"><span data-stu-id="489f8-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="489f8-104">Ta metoda jest przestarzała w .NET Framework w wersji 2,0.</span><span class="sxs-lookup"><span data-stu-id="489f8-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="489f8-105">Zamiast tego użyj [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs —](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="489f8-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="489f8-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="489f8-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="489f8-107">Parametry</span><span class="sxs-lookup"><span data-stu-id="489f8-107">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="489f8-108">podczas Identyfikator modułu, który zawiera klasę.</span><span class="sxs-lookup"><span data-stu-id="489f8-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="489f8-109">podczas `mdTypeDef` Token metadanych, który odwołuje się do klasy.</span><span class="sxs-lookup"><span data-stu-id="489f8-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="489f8-110">określoną Wskaźnik do identyfikatora klasy.</span><span class="sxs-lookup"><span data-stu-id="489f8-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="489f8-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="489f8-111">Remarks</span></span>  

 <span data-ttu-id="489f8-112">Ta metoda jest przestarzała; Zamiast tego należy używać `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` dla wszystkich typów.</span><span class="sxs-lookup"><span data-stu-id="489f8-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="489f8-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="489f8-113">Requirements</span></span>  

 <span data-ttu-id="489f8-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="489f8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="489f8-115">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="489f8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="489f8-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="489f8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="489f8-117">**.NET Framework wersje:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="489f8-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="489f8-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="489f8-118">See also</span></span>

- [<span data-ttu-id="489f8-119">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="489f8-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
