---
title: ICorDebugManagedCallback2::FunctionRemapComplete — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type:
- apiref
ms.openlocfilehash: 7eb7fb55a5077d2914eb85a67ca62163a1aa8cc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704607"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="d4a98-102">ICorDebugManagedCallback2::FunctionRemapComplete — Metoda</span><span class="sxs-lookup"><span data-stu-id="d4a98-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>

<span data-ttu-id="d4a98-103">Powiadamia debuger, że wykonywanie kodu zostało przełączone do nowej wersji edytowanej funkcji.</span><span class="sxs-lookup"><span data-stu-id="d4a98-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4a98-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d4a98-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4a98-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d4a98-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="d4a98-106">podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji zawierającą edytowaną funkcję.</span><span class="sxs-lookup"><span data-stu-id="d4a98-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="d4a98-107">podczas Wskaźnik do obiektu ICorDebugThread, który reprezentuje wątek, w którym napotkano punkt przerwania mapowania.</span><span class="sxs-lookup"><span data-stu-id="d4a98-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="d4a98-108">podczas Wskaźnik do obiektu ICorDebugFunction, który reprezentuje wersję funkcji aktualnie uruchomionej w wątku.</span><span class="sxs-lookup"><span data-stu-id="d4a98-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4a98-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d4a98-109">Remarks</span></span>  

 <span data-ttu-id="d4a98-110">To wywołanie zwrotne daje debugerowi możliwość ponownego utworzenia wszystkich, które wcześniej istniały.</span><span class="sxs-lookup"><span data-stu-id="d4a98-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4a98-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d4a98-111">Requirements</span></span>  

 <span data-ttu-id="d4a98-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4a98-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4a98-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="d4a98-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4a98-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d4a98-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4a98-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4a98-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4a98-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d4a98-116">See also</span></span>

- [<span data-ttu-id="d4a98-117">ICorDebugManagedCallback2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d4a98-117">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="d4a98-118">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d4a98-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
