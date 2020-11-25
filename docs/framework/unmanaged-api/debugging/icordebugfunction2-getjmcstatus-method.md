---
title: ICorDebugFunction2::GetJMCStatus — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 747f165a98dfd1264ea58d61aaa1615c6d71e073
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726299"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="cb8c3-102">ICorDebugFunction2::GetJMCStatus — Metoda</span><span class="sxs-lookup"><span data-stu-id="cb8c3-102">ICorDebugFunction2::GetJMCStatus Method</span></span>

<span data-ttu-id="cb8c3-103">Pobiera wartość wskazującą, czy funkcja reprezentowana przez ten obiekt ICorDebugFunction2 jest oznaczona jako kod użytkownika.</span><span class="sxs-lookup"><span data-stu-id="cb8c3-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb8c3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cb8c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb8c3-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="cb8c3-105">Parameters</span></span>  

 `pbIsJustMyCode`  
 <span data-ttu-id="cb8c3-106">określoną Wskaźnik do wartości logicznej, która jest `true` oznaczona jako kod użytkownika; w przeciwnym razie wartość to `false` .</span><span class="sxs-lookup"><span data-stu-id="cb8c3-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb8c3-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cb8c3-107">Remarks</span></span>  

 <span data-ttu-id="cb8c3-108">Jeśli funkcja reprezentowana przez to `ICorDebugFunction2` nie może być debugowana, `pbIsJustMyCode` będzie zawsze `false` .</span><span class="sxs-lookup"><span data-stu-id="cb8c3-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb8c3-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cb8c3-109">Requirements</span></span>  

 <span data-ttu-id="cb8c3-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb8c3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb8c3-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="cb8c3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb8c3-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="cb8c3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb8c3-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb8c3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
