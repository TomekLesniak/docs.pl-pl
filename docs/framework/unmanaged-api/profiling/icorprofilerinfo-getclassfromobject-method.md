---
title: ICorProfilerInfo::GetClassFromObject — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
ms.openlocfilehash: 5a7edc6045969861679d1b80c0563e99f48932cf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680251"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="87b91-102">ICorProfilerInfo::GetClassFromObject — Metoda</span><span class="sxs-lookup"><span data-stu-id="87b91-102">ICorProfilerInfo::GetClassFromObject Method</span></span>

<span data-ttu-id="87b91-103">Pobiera `ClassID` obiekt z danego obiektu `ObjectID` .</span><span class="sxs-lookup"><span data-stu-id="87b91-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87b91-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="87b91-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87b91-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="87b91-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="87b91-106">podczas Identyfikator obiektu, dla którego ma zostać pobrany `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="87b91-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="87b91-107">określoną Wskaźnik do zwracanego elementu `ClassID` .</span><span class="sxs-lookup"><span data-stu-id="87b91-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87b91-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="87b91-108">Remarks</span></span>  

 <span data-ttu-id="87b91-109">Wartość null `pClassId` wskazuje `objectId` Typ, który jest wyładowania.</span><span class="sxs-lookup"><span data-stu-id="87b91-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87b91-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="87b91-110">Requirements</span></span>  

 <span data-ttu-id="87b91-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87b91-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87b91-112">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="87b91-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="87b91-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="87b91-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87b91-114">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87b91-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b91-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="87b91-115">See also</span></span>

- [<span data-ttu-id="87b91-116">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="87b91-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
