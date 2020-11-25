---
title: ICorProfilerInfo::SetEventMask — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type:
- apiref
ms.openlocfilehash: 9d319b6523b2c2a1bcc5cb6ea7a28efa67d898e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720951"
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="5ecb5-102">ICorProfilerInfo::SetEventMask — Metoda</span><span class="sxs-lookup"><span data-stu-id="5ecb5-102">ICorProfilerInfo::SetEventMask Method</span></span>

<span data-ttu-id="5ecb5-103">Ustawia wartość określającą typy zdarzeń, dla których profiler chce otrzymywać powiadomienia z aparatu plików wykonywalnych języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="5ecb5-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ecb5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5ecb5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ecb5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="5ecb5-105">Parameters</span></span>  

 `dwEvents`  
 <span data-ttu-id="5ecb5-106">podczas Wartość 4-bajtowa, która określa kategorie zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="5ecb5-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="5ecb5-107">Każdy bit steruje inną możliwością, zachowaniem lub typem zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="5ecb5-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="5ecb5-108">Bity są opisane w [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) Wyliczenie.</span><span class="sxs-lookup"><span data-stu-id="5ecb5-108">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ecb5-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5ecb5-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5ecb5-110">Zamiast tej metody należy wywołać metodę [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5ecb5-110">You should call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="5ecb5-111">Mimo że `SetEventMask` metoda nadal jest obsługiwana, [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) oferuje dodatkowe funkcje.</span><span class="sxs-lookup"><span data-stu-id="5ecb5-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ecb5-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5ecb5-112">Requirements</span></span>  

 <span data-ttu-id="5ecb5-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ecb5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ecb5-114">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="5ecb5-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5ecb5-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5ecb5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ecb5-116">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ecb5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ecb5-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5ecb5-117">See also</span></span>

- [<span data-ttu-id="5ecb5-118">ICorProfilerInfo — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5ecb5-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="5ecb5-119">SetEventMask2, metoda</span><span class="sxs-lookup"><span data-stu-id="5ecb5-119">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
