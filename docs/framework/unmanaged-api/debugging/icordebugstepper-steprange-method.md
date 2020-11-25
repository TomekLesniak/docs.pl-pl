---
title: ICorDebugStepper::StepRange — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
ms.openlocfilehash: d9698afa2723a5d772ecf5a055f09c5ee3bc13f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727656"
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="ba8d2-102">ICorDebugStepper::StepRange — Metoda</span><span class="sxs-lookup"><span data-stu-id="ba8d2-102">ICorDebugStepper::StepRange Method</span></span>

<span data-ttu-id="ba8d2-103">Powoduje, że ICorDebugStepper to jeden krok za pomocą zawartego w nim wątku i zwraca, gdy osiągnie kod poza ostatnim z określonych zakresów.</span><span class="sxs-lookup"><span data-stu-id="ba8d2-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba8d2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ba8d2-104">Syntax</span></span>  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba8d2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ba8d2-105">Parameters</span></span>  

 `bStepIn`  
 <span data-ttu-id="ba8d2-106">podczas Ustaw, aby `true` wkroczyć do funkcji, która jest wywoływana w wątku.</span><span class="sxs-lookup"><span data-stu-id="ba8d2-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="ba8d2-107">Ustaw, aby przekroczyć `false` funkcję.</span><span class="sxs-lookup"><span data-stu-id="ba8d2-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="ba8d2-108">podczas Tablica struktur COR_DEBUG_STEP_RANGE, z których każdy określa zakres.</span><span class="sxs-lookup"><span data-stu-id="ba8d2-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="ba8d2-109">podczas Rozmiar `ranges` tablicy.</span><span class="sxs-lookup"><span data-stu-id="ba8d2-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba8d2-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ba8d2-110">Remarks</span></span>  

 <span data-ttu-id="ba8d2-111">`StepRange`Metoda działa jak Metoda [ICorDebugStepper:: Step](icordebugstepper-step-method.md) , z tą różnicą, że nie zostanie ukończona, dopóki nie zostanie osiągnięty kod poza podanym zakresem.</span><span class="sxs-lookup"><span data-stu-id="ba8d2-111">The `StepRange` method works like the [ICorDebugStepper::Step](icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="ba8d2-112">Może to być wydajniejsze niż wykonywanie jednej instrukcji w danym momencie.</span><span class="sxs-lookup"><span data-stu-id="ba8d2-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="ba8d2-113">Zakresy są określone jako lista par przesunięcia od początku ramki stepper.</span><span class="sxs-lookup"><span data-stu-id="ba8d2-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="ba8d2-114">Zakresy są względne dla kodu języka pośredniego firmy Microsoft (MSIL) metody.</span><span class="sxs-lookup"><span data-stu-id="ba8d2-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="ba8d2-115">Wywołanie [ICorDebugStepper:: SetRangeIL —](icordebugstepper-setrangeil-method.md) z, `false` Aby uczynić zakresy względem kodu natywnego metody.</span><span class="sxs-lookup"><span data-stu-id="ba8d2-115">Call [ICorDebugStepper::SetRangeIL](icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba8d2-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ba8d2-116">Requirements</span></span>  

 <span data-ttu-id="ba8d2-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba8d2-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba8d2-118">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ba8d2-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba8d2-119">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ba8d2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba8d2-120">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba8d2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
