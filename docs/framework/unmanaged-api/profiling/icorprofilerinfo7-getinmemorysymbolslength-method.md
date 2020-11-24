---
title: 'ICorProfilerInfo7:: GetInMemorySymbolsLength, Metoda'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
ms.openlocfilehash: 46ffa5cb4fac6988240d32cb1939cc25bdf0a412
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686075"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="f1f80-102">ICorProfilerInfo7:: GetInMemorySymbolsLength, Metoda</span><span class="sxs-lookup"><span data-stu-id="f1f80-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>

<span data-ttu-id="f1f80-103">[Obsługiwane w .NET Framework 4.6.1 i nowszych wersjach]</span><span class="sxs-lookup"><span data-stu-id="f1f80-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="f1f80-104">Zwraca długość strumienia symboli w pamięci.</span><span class="sxs-lookup"><span data-stu-id="f1f80-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1f80-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="f1f80-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1f80-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="f1f80-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="f1f80-107">podczas Identyfikator modułu zawierającego strumień znajdujący się w pamięci.</span><span class="sxs-lookup"><span data-stu-id="f1f80-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="f1f80-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="f1f80-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="f1f80-109">określoną Wskaźnik do `DWORD` wartości, która, gdy zwraca metodę, zawiera długość strumienia w bajtach.</span><span class="sxs-lookup"><span data-stu-id="f1f80-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1f80-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="f1f80-110">Return Value</span></span>  

 <span data-ttu-id="f1f80-111">Metoda zwraca `S_OK` , jeśli długość strumienia pamięci można ustalić, nawet jeśli jest równa zero (0).</span><span class="sxs-lookup"><span data-stu-id="f1f80-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="f1f80-112">Metoda zwraca, `CORPROF_E_MODULE_IS_DYNAMIC` Jeśli metoda została utworzona przy użyciu <xref:System.Reflection.Emit?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f1f80-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1f80-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f1f80-113">Remarks</span></span>  

 <span data-ttu-id="f1f80-114">Jeśli moduł zawiera symbole w pamięci, długość strumienia jest umieszczana w `pCountSymbolBytes` .</span><span class="sxs-lookup"><span data-stu-id="f1f80-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="f1f80-115">Jeśli moduł nie zawiera symboli w pamięci, `*pCountSymbolBytes = 0` .</span><span class="sxs-lookup"><span data-stu-id="f1f80-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1f80-116">Bieżąca implementacja nie obsługuje odbicia. emisji.</span><span class="sxs-lookup"><span data-stu-id="f1f80-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="f1f80-117">Jeśli moduł został utworzony przy użyciu odbicia. Emituj, metoda zwraca `CORPROF_E_MODULE_IS_DYNAMIC` .</span><span class="sxs-lookup"><span data-stu-id="f1f80-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1f80-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f1f80-118">Requirements</span></span>  

 <span data-ttu-id="f1f80-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1f80-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1f80-120">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="f1f80-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1f80-121">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f1f80-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1f80-122">**.NET Framework wersje:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1f80-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1f80-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f1f80-123">See also</span></span>

- [<span data-ttu-id="f1f80-124">ICorProfilerInfo7, interfejs</span><span class="sxs-lookup"><span data-stu-id="f1f80-124">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
