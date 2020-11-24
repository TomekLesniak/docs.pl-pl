---
title: ICorDebugFrame::GetChain — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetChain
helpviewer_keywords:
- ICorDebugFrame::GetChain method [.NET Framework debugging]
- GetChain method [.NET Framework debugging]
ms.assetid: e28e51d3-8f73-494f-bcd4-48bac239fbe1
topic_type:
- apiref
ms.openlocfilehash: d605ac36c17a815bf546819e331830f51142cfcd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690424"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="510e7-102">ICorDebugFrame::GetChain — Metoda</span><span class="sxs-lookup"><span data-stu-id="510e7-102">ICorDebugFrame::GetChain Method</span></span>

<span data-ttu-id="510e7-103">Pobiera wskaźnik do łańcucha, do którego należy ta ramka.</span><span class="sxs-lookup"><span data-stu-id="510e7-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="510e7-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="510e7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="510e7-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="510e7-105">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="510e7-106">określoną Wskaźnik do adresu obiektu ICorDebugChain, który reprezentuje łańcuch zawierający tę ramkę.</span><span class="sxs-lookup"><span data-stu-id="510e7-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="510e7-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="510e7-107">Requirements</span></span>  

 <span data-ttu-id="510e7-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="510e7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="510e7-109">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="510e7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="510e7-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="510e7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="510e7-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="510e7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
