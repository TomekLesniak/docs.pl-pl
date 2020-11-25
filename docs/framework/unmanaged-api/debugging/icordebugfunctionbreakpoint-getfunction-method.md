---
title: ICorDebugFunctionBreakpoint::GetFunction — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetFunction
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetFunction method [.NET Framework debugging]
- GetFunction method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 2a62dae5-dd8a-4696-b817-0e1e586c24a0
topic_type:
- apiref
ms.openlocfilehash: 4ef5728e4b13d6d3d73aef06f9f7f50ab22609ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726265"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="332a7-102">ICorDebugFunctionBreakpoint::GetFunction — Metoda</span><span class="sxs-lookup"><span data-stu-id="332a7-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>

<span data-ttu-id="332a7-103">Pobiera wskaźnik interfejsu do elementu ICorDebugFunction, który odwołuje się do funkcji, w której jest ustawiony punkt przerwania.</span><span class="sxs-lookup"><span data-stu-id="332a7-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="332a7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="332a7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="332a7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="332a7-105">Parameters</span></span>  

 `ppFunction`  
 <span data-ttu-id="332a7-106">określoną Wskaźnik do adresu funkcji, w której jest ustawiony punkt przerwania.</span><span class="sxs-lookup"><span data-stu-id="332a7-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="332a7-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="332a7-107">Requirements</span></span>  

 <span data-ttu-id="332a7-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="332a7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="332a7-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="332a7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="332a7-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="332a7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="332a7-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="332a7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
