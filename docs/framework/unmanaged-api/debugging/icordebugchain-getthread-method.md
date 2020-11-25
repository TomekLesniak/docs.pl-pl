---
title: ICorDebugChain::GetThread — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type:
- apiref
ms.openlocfilehash: ad220289b45078130a0a41e67373fd3384ae9682
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724419"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="d2c45-102">ICorDebugChain::GetThread — Metoda</span><span class="sxs-lookup"><span data-stu-id="d2c45-102">ICorDebugChain::GetThread Method</span></span>

<span data-ttu-id="d2c45-103">Pobiera wątek fizyczny, do którego należy ten łańcuch wywołań.</span><span class="sxs-lookup"><span data-stu-id="d2c45-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2c45-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d2c45-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2c45-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d2c45-105">Parameters</span></span>  

 `ppThread`  
 <span data-ttu-id="d2c45-106">określoną Wskaźnik do obiektu ICorDebugThread, który reprezentuje wątek fizyczny, do którego należy ten łańcuch wywołań.</span><span class="sxs-lookup"><span data-stu-id="d2c45-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2c45-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d2c45-107">Requirements</span></span>  

 <span data-ttu-id="d2c45-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2c45-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2c45-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="d2c45-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2c45-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d2c45-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2c45-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2c45-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
