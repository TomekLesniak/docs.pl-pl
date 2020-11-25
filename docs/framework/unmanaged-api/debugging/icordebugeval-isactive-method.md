---
title: ICorDebugEval::IsActive — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugEval.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type:
- apiref
ms.openlocfilehash: 5ac221b0b5837175b8073ab29f94c1f28078d3e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729775"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="ddbbd-102">ICorDebugEval::IsActive — Metoda</span><span class="sxs-lookup"><span data-stu-id="ddbbd-102">ICorDebugEval::IsActive Method</span></span>

<span data-ttu-id="ddbbd-103">Pobiera wartość wskazującą, czy ten obiekt ICorDebugEval jest aktualnie wykonywany.</span><span class="sxs-lookup"><span data-stu-id="ddbbd-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddbbd-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ddbbd-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddbbd-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ddbbd-105">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="ddbbd-106">określoną Wskaźnik na wartość wskazującą, czy ta Ocena jest aktywna.</span><span class="sxs-lookup"><span data-stu-id="ddbbd-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddbbd-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ddbbd-107">Requirements</span></span>  

 <span data-ttu-id="ddbbd-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddbbd-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddbbd-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="ddbbd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ddbbd-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ddbbd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddbbd-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddbbd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
