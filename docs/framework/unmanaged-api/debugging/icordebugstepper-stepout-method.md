---
title: ICorDebugStepper::StepOut — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
ms.openlocfilehash: 1396e7a8ca61734a9363a9c852502290675249d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727669"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="7c0db-102">ICorDebugStepper::StepOut — Metoda</span><span class="sxs-lookup"><span data-stu-id="7c0db-102">ICorDebugStepper::StepOut Method</span></span>

<span data-ttu-id="7c0db-103">Powoduje, że ICorDebugStepper to jeden krok za pomocą zawartego w nim wątku oraz do zakończenia, gdy bieżąca ramka zwraca sterowanie do ramki wywołującej.</span><span class="sxs-lookup"><span data-stu-id="7c0db-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c0db-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7c0db-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="7c0db-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7c0db-105">Remarks</span></span>  

 <span data-ttu-id="7c0db-106">Operacja zakończy `StepOut` się po powrocie z bieżącej ramki do ramki wywołującej.</span><span class="sxs-lookup"><span data-stu-id="7c0db-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="7c0db-107">Jeśli `StepOut` jest wywoływana w kodzie niezarządzanym, krok zakończy się, gdy bieżąca ramka powróci do zarządzanego kodu, który go wywołał.</span><span class="sxs-lookup"><span data-stu-id="7c0db-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="7c0db-108">W .NET Framework w wersji 2,0 nie należy używać `StepOut` z ustawioną flagą STOP_UNMANAGED, ponieważ zakończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="7c0db-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="7c0db-109">(Użyj [ICorDebugStepper:: SetUnmappedStopMask —](icordebugstepper-setunmappedstopmask-method.md) , aby ustawić flagi do wykonywania krokowo). Debugery międzyoperacyjności muszą przekroczyć kod natywny.</span><span class="sxs-lookup"><span data-stu-id="7c0db-109">(Use [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c0db-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7c0db-110">Requirements</span></span>  

 <span data-ttu-id="7c0db-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c0db-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c0db-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="7c0db-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c0db-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="7c0db-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c0db-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c0db-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
