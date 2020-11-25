---
title: ICorDebugILFrame2::RemapFunction — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
ms.openlocfilehash: 5eb6299526d69624056961cfb7f0387ff8f873cf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725030"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="97d1b-102">ICorDebugILFrame2::RemapFunction — Metoda</span><span class="sxs-lookup"><span data-stu-id="97d1b-102">ICorDebugILFrame2::RemapFunction Method</span></span>

<span data-ttu-id="97d1b-103">Ponownie mapuje edytowaną funkcję poprzez określenie nowego przesunięcia języka pośredniego firmy Microsoft (MSIL)</span><span class="sxs-lookup"><span data-stu-id="97d1b-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97d1b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="97d1b-104">Syntax</span></span>  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97d1b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="97d1b-105">Parameters</span></span>  

 `newILOffset`  
 <span data-ttu-id="97d1b-106">podczas Nowe przesunięcie MSIL ramki stosu, w którym należy umieścić wskaźnik instrukcji.</span><span class="sxs-lookup"><span data-stu-id="97d1b-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="97d1b-107">Ta wartość musi być punktem sekwencji.</span><span class="sxs-lookup"><span data-stu-id="97d1b-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="97d1b-108">Jest on odpowiedzialny za zagwarantowanie ważności tej wartości.</span><span class="sxs-lookup"><span data-stu-id="97d1b-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="97d1b-109">Na przykład przesunięcie MSIL jest nieprawidłowe, jeśli znajduje się poza granicami funkcji.</span><span class="sxs-lookup"><span data-stu-id="97d1b-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97d1b-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="97d1b-110">Remarks</span></span>  

 <span data-ttu-id="97d1b-111">Po edytowaniu funkcji ramki debuger może wywołać `RemapFunction` metodę, aby dokonać zamiany w najnowszej wersji funkcji ramki, aby można ją było wykonać.</span><span class="sxs-lookup"><span data-stu-id="97d1b-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="97d1b-112">Wykonanie kodu rozpocznie się w danym przesunięciu MSIL.</span><span class="sxs-lookup"><span data-stu-id="97d1b-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97d1b-113">Wywołanie `RemapFunction` , takie jak wywołanie [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md), natychmiast unieważnia wszystkie interfejsy debugowania, które są związane z generowaniem śladu stosu dla wątku.</span><span class="sxs-lookup"><span data-stu-id="97d1b-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="97d1b-114">Te interfejsy obejmują [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame i ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="97d1b-114">These interfaces include [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="97d1b-115">`RemapFunction`Metodę można wywołać tylko w kontekście bieżącej ramki i tylko w jednym z następujących przypadków:</span><span class="sxs-lookup"><span data-stu-id="97d1b-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="97d1b-116">Po odebraniu wywołania zwrotnego [ICorDebugManagedCallback2:: FunctionRemapOpportunity —](icordebugmanagedcallback2-functionremapopportunity-method.md) , które nie było jeszcze kontynuowane.</span><span class="sxs-lookup"><span data-stu-id="97d1b-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="97d1b-117">Mimo że wykonywanie kodu zostało zatrzymane z powodu zdarzenia [ICorDebugManagedCallback:: EditAndContinueRemap —](icordebugmanagedcallback-editandcontinueremap-method.md) dla tej ramki.</span><span class="sxs-lookup"><span data-stu-id="97d1b-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97d1b-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="97d1b-118">Requirements</span></span>  

 <span data-ttu-id="97d1b-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97d1b-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97d1b-120">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="97d1b-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97d1b-121">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="97d1b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97d1b-122">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97d1b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
