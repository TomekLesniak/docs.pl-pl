---
title: ICorDebugChain::GetCallee — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
ms.openlocfilehash: a28da34cd3080826f346b8957aa6ba38258b924f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730126"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="43d0e-102">ICorDebugChain::GetCallee — Metoda</span><span class="sxs-lookup"><span data-stu-id="43d0e-102">ICorDebugChain::GetCallee Method</span></span>

<span data-ttu-id="43d0e-103">Pobiera łańcuch, który został wywołany przez ten łańcuch.</span><span class="sxs-lookup"><span data-stu-id="43d0e-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43d0e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="43d0e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43d0e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="43d0e-105">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="43d0e-106">określoną Wskaźnik do adresu obiektu ICorDebugChain, który reprezentuje wywołany łańcuch.</span><span class="sxs-lookup"><span data-stu-id="43d0e-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="43d0e-107">Jeśli ten łańcuch jest obecnie wykonywany (oznacza to, że jeśli ten łańcuch nie oczekuje na zwrócenie wywołanego łańcucha), `ppChain` będzie miał wartość null.</span><span class="sxs-lookup"><span data-stu-id="43d0e-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43d0e-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="43d0e-108">Remarks</span></span>  

 <span data-ttu-id="43d0e-109">Ten łańcuch będzie czekał na zwrócenie wywoływanego łańcucha przed wznowieniem wykonywania.</span><span class="sxs-lookup"><span data-stu-id="43d0e-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="43d0e-110">Wywołany łańcuch może znajdować się w innym wątku w przypadku wywołań zorganizowanych między wątkami.</span><span class="sxs-lookup"><span data-stu-id="43d0e-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43d0e-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="43d0e-111">Requirements</span></span>  

 <span data-ttu-id="43d0e-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43d0e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43d0e-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="43d0e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43d0e-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="43d0e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43d0e-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43d0e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
