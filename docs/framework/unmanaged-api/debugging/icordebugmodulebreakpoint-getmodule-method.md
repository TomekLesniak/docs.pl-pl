---
title: ICorDebugModuleBreakpoint::GetModule — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type:
- apiref
ms.openlocfilehash: b6363ef901d5297862ca46e685bb783aaaeb4123
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709625"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="ad933-102">ICorDebugModuleBreakpoint::GetModule — Metoda</span><span class="sxs-lookup"><span data-stu-id="ad933-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>

<span data-ttu-id="ad933-103">Pobiera wskaźnik interfejsu do "ICorDebugModule", który odwołuje się do modułu, w którym jest ustawiony ten punkt przerwania.</span><span class="sxs-lookup"><span data-stu-id="ad933-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad933-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ad933-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad933-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ad933-105">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="ad933-106">określoną Wskaźnik do adresu `ICorDebugModule` interfejsu, który odwołuje się do modułu, w którym jest ustawiony punkt przerwania.</span><span class="sxs-lookup"><span data-stu-id="ad933-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad933-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ad933-107">Requirements</span></span>  

 <span data-ttu-id="ad933-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad933-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad933-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ad933-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad933-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ad933-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad933-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad933-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad933-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ad933-112">See also</span></span>
