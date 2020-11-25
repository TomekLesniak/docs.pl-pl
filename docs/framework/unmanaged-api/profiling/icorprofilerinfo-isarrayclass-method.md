---
title: ICorProfilerInfo::IsArrayClass — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
ms.openlocfilehash: 2608f91a7c5baa935e48fbe58ad4d14aaaad1f0d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722508"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="86f16-102">ICorProfilerInfo::IsArrayClass — Metoda</span><span class="sxs-lookup"><span data-stu-id="86f16-102">ICorProfilerInfo::IsArrayClass Method</span></span>

<span data-ttu-id="86f16-103">Określa, czy określona Klasa jest klasą Array.</span><span class="sxs-lookup"><span data-stu-id="86f16-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86f16-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="86f16-104">Syntax</span></span>  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86f16-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="86f16-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="86f16-106">podczas Identyfikator klasy, która ma zostać zbadana.</span><span class="sxs-lookup"><span data-stu-id="86f16-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="86f16-107">określoną Wskaźnik do wartości wyliczenia CorElementType —, który wskazuje typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="86f16-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="86f16-108">określoną Wskaźnik do identyfikatora klasy elementów tablicy, jeśli jest dostępny.</span><span class="sxs-lookup"><span data-stu-id="86f16-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="86f16-109">określoną Wskaźnik do liczby całkowitej, która wskazuje rangę (czyli liczbę wymiarów) tablicy.</span><span class="sxs-lookup"><span data-stu-id="86f16-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86f16-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="86f16-110">Remarks</span></span>  

 <span data-ttu-id="86f16-111">Jeśli określona Klasa jest klasą Array, `IsArrayClass` Metoda zwraca S_OK HRESULT i wartości dla wszystkich parametrów wyjściowych o wartości innej niż null.</span><span class="sxs-lookup"><span data-stu-id="86f16-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="86f16-112">W przeciwnym razie zwraca S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="86f16-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86f16-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="86f16-113">Requirements</span></span>  

 <span data-ttu-id="86f16-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86f16-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86f16-115">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="86f16-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="86f16-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="86f16-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86f16-117">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86f16-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86f16-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="86f16-118">See also</span></span>

- [<span data-ttu-id="86f16-119">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="86f16-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
