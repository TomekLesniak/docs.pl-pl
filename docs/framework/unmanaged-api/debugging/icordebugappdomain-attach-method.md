---
title: ICorDebugAppDomain::Attach — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.Attach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::Attach
helpviewer_keywords:
- ICorDebugAppDomain::Attach method [.NET Framework debugging]
- Attach method [.NET Framework debugging]
ms.assetid: 0358b84a-4236-4c34-945b-4babff7df570
topic_type:
- apiref
ms.openlocfilehash: d133cacb611a1c7bd03d7653f46c2e5fb1acc043
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723353"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="0274c-102">ICorDebugAppDomain::Attach — Metoda</span><span class="sxs-lookup"><span data-stu-id="0274c-102">ICorDebugAppDomain::Attach Method</span></span>

<span data-ttu-id="0274c-103">Dołącza debuger do domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0274c-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0274c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0274c-104">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0274c-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0274c-105">Remarks</span></span>  

 <span data-ttu-id="0274c-106">Debuger musi być dołączony do domeny aplikacji, aby odbierać zdarzenia i włączać debugowanie domeny aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0274c-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0274c-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0274c-107">Requirements</span></span>  

 <span data-ttu-id="0274c-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0274c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0274c-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="0274c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0274c-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0274c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0274c-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0274c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
