---
title: ICorDebugThread::GetActiveFrame — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
ms.openlocfilehash: 6ca4c1ad5ef575db075a5066146bacb6d1e59ea2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728085"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="96de9-102">ICorDebugThread::GetActiveFrame — Metoda</span><span class="sxs-lookup"><span data-stu-id="96de9-102">ICorDebugThread::GetActiveFrame Method</span></span>

<span data-ttu-id="96de9-103">Pobiera wskaźnik interfejsu do aktywnej (najnowszej) ramki tego obiektu ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="96de9-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96de9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="96de9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96de9-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="96de9-105">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="96de9-106">określoną Wskaźnik do adresu obiektu interfejsu ICorDebugFrame, który reprezentuje ramkę.</span><span class="sxs-lookup"><span data-stu-id="96de9-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96de9-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="96de9-107">Remarks</span></span>  

 <span data-ttu-id="96de9-108">`ppFrame`Parametr ma wartość null, jeśli żadna ramka nie jest obecnie aktywna.</span><span class="sxs-lookup"><span data-stu-id="96de9-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96de9-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="96de9-109">Requirements</span></span>  

 <span data-ttu-id="96de9-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96de9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96de9-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="96de9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96de9-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="96de9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96de9-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96de9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
