---
title: ICorDebugManagedCallback::CreateProcess — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type:
- apiref
ms.openlocfilehash: cd24e672c65769586dc618c21503dbb344566974
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731816"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="1cfc5-102">ICorDebugManagedCallback::CreateProcess — Metoda</span><span class="sxs-lookup"><span data-stu-id="1cfc5-102">ICorDebugManagedCallback::CreateProcess Method</span></span>

<span data-ttu-id="1cfc5-103">Powiadamia debuger, gdy proces został dołączony lub uruchomiony po raz pierwszy.</span><span class="sxs-lookup"><span data-stu-id="1cfc5-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cfc5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1cfc5-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cfc5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="1cfc5-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="1cfc5-106">podczas Wskaźnik do obiektu ICorDebugProcess, który reprezentuje proces, który został dołączony lub uruchomiony.</span><span class="sxs-lookup"><span data-stu-id="1cfc5-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cfc5-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1cfc5-107">Remarks</span></span>  

 <span data-ttu-id="1cfc5-108">Ta metoda nie jest wywoływana do momentu zainicjowania środowiska uruchomieniowego języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="1cfc5-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="1cfc5-109">Większość metod [ICorDebug](icordebug-interface.md) zwróci wartość CORDBG_E_NOTREADY przed `CreateProcess` wywołaniem zwrotnym.</span><span class="sxs-lookup"><span data-stu-id="1cfc5-109">Most of the [ICorDebug](icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cfc5-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1cfc5-110">Requirements</span></span>  

 <span data-ttu-id="1cfc5-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cfc5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cfc5-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="1cfc5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1cfc5-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="1cfc5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cfc5-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cfc5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cfc5-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1cfc5-115">See also</span></span>

- [<span data-ttu-id="1cfc5-116">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="1cfc5-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
