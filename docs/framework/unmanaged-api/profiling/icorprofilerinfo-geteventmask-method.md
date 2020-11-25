---
title: ICorProfilerInfo::GetEventMask — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetEventMask
helpviewer_keywords:
- GetEventMask method [.NET Framework profiling]
- ICorProfilerInfo::GetEventMask method [.NET Framework profiling]
ms.assetid: ec34cc13-45a3-4695-abc3-b3347d4e6fc2
topic_type:
- apiref
ms.openlocfilehash: 16bd8b09d5118171e669e9c428fb444384b5867d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722573"
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="c8369-102">ICorProfilerInfo::GetEventMask — Metoda</span><span class="sxs-lookup"><span data-stu-id="c8369-102">ICorProfilerInfo::GetEventMask Method</span></span>

<span data-ttu-id="c8369-103">Pobiera bieżące kategorie zdarzeń, dla których profiler chce otrzymywać powiadomienia o zdarzeniach z aparatu plików wykonywalnych języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="c8369-103">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8369-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c8369-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8369-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c8369-105">Parameters</span></span>  

 `pdwEvents`  
 <span data-ttu-id="c8369-106">określoną Wskaźnik do 4-bajtowej wartości, która określa kategorie zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="c8369-106">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="c8369-107">Każdy bit steruje inną możliwością, zachowaniem lub typem zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="c8369-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="c8369-108">Bity są opisane w [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) Wyliczenie.</span><span class="sxs-lookup"><span data-stu-id="c8369-108">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8369-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c8369-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8369-110">Zamiast tej metody należy wywołać metodę [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c8369-110">You should call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="c8369-111">Mimo że `SetEventMask` metoda nadal jest obsługiwana, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) oferuje dodatkowe funkcje.</span><span class="sxs-lookup"><span data-stu-id="c8369-111">Although the `SetEventMask` method continues to be supported, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8369-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c8369-112">Requirements</span></span>  

 <span data-ttu-id="c8369-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8369-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8369-114">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="c8369-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c8369-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c8369-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8369-116">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8369-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8369-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c8369-117">See also</span></span>

- [<span data-ttu-id="c8369-118">GetEventMask2, metoda</span><span class="sxs-lookup"><span data-stu-id="c8369-118">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
- [<span data-ttu-id="c8369-119">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c8369-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
