---
title: ICorDebugChain::EnumerateFrames — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
ms.openlocfilehash: ae6d81e6fdab0f8e3346d8a08a3b5ebc329a542a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730152"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="523b3-102">ICorDebugChain::EnumerateFrames — Metoda</span><span class="sxs-lookup"><span data-stu-id="523b3-102">ICorDebugChain::EnumerateFrames Method</span></span>

<span data-ttu-id="523b3-103">Pobiera moduł wyliczający, który zawiera wszystkie zarządzane ramki stosu w łańcuchu, rozpoczynając od ostatniej ramki.</span><span class="sxs-lookup"><span data-stu-id="523b3-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="523b3-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="523b3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="523b3-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="523b3-105">Parameters</span></span>  

 `ppFrames`  
 <span data-ttu-id="523b3-106">określoną Wskaźnik do adresu obiektu ICorDebugFrameEnum, który jest modułem wyliczającym dla ramek stosu.</span><span class="sxs-lookup"><span data-stu-id="523b3-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="523b3-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="523b3-107">Remarks</span></span>  

 <span data-ttu-id="523b3-108">Łańcuch reprezentuje stos wywołań fizycznych wątku.</span><span class="sxs-lookup"><span data-stu-id="523b3-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="523b3-109">`EnumerateFrames`Metoda powinna być wywoływana tylko dla łańcuchów zarządzanych.</span><span class="sxs-lookup"><span data-stu-id="523b3-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="523b3-110">Interfejs API debugowania nie udostępnia metod uzyskiwania ramek zawartych w łańcuchach niezarządzanych.</span><span class="sxs-lookup"><span data-stu-id="523b3-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="523b3-111">Aby uzyskać te informacje, debuger musi użyć innych metod.</span><span class="sxs-lookup"><span data-stu-id="523b3-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="523b3-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="523b3-112">Requirements</span></span>  

 <span data-ttu-id="523b3-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="523b3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="523b3-114">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="523b3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="523b3-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="523b3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="523b3-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="523b3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
