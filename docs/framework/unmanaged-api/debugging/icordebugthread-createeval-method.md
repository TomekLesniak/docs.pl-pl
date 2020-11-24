---
title: ICorDebugThread::CreateEval — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
ms.openlocfilehash: 1c0037530ae4f40be5bef4da8f398afe5f2bbb91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688292"
---
# <a name="icordebugthreadcreateeval-method"></a><span data-ttu-id="84c65-102">ICorDebugThread::CreateEval — Metoda</span><span class="sxs-lookup"><span data-stu-id="84c65-102">ICorDebugThread::CreateEval Method</span></span>

<span data-ttu-id="84c65-103">Tworzy obiekt ICorDebugEval, który zbiera i udostępnia funkcje tego ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="84c65-103">Creates an ICorDebugEval object that collects and exposes the functionality of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84c65-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="84c65-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84c65-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="84c65-105">Parameters</span></span>  

 `ppEval`  
 <span data-ttu-id="84c65-106">określoną Wskaźnik do adresu `ICorDebugEval` obiektu, który zbiera i udostępnia funkcjonalność tego wątku.</span><span class="sxs-lookup"><span data-stu-id="84c65-106">[out] A pointer to the address of an `ICorDebugEval` object that collects and exposes the functionality of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84c65-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="84c65-107">Remarks</span></span>  

 <span data-ttu-id="84c65-108">Obiekt oceny wypycha nowy łańcuch w wątku przed wykonaniem jego obliczenia.</span><span class="sxs-lookup"><span data-stu-id="84c65-108">The evaluation object will push a new chain on the thread before doing its computation.</span></span> <span data-ttu-id="84c65-109">Spowoduje to przerwanie obliczeń aktualnie wykonywanych na wątku do momentu zakończenia szacowania.</span><span class="sxs-lookup"><span data-stu-id="84c65-109">This interrupts the computation currently being performed on the thread until the evaluation completes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84c65-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="84c65-110">Requirements</span></span>  

 <span data-ttu-id="84c65-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84c65-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84c65-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="84c65-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84c65-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="84c65-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84c65-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84c65-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
