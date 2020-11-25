---
title: ICorDebugProcess::GetThreadContext — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
ms.openlocfilehash: 3be689e5c1474bcbfbca72a14a298762dc2e7a90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724549"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="74484-102">ICorDebugProcess::GetThreadContext — Metoda</span><span class="sxs-lookup"><span data-stu-id="74484-102">ICorDebugProcess::GetThreadContext Method</span></span>

<span data-ttu-id="74484-103">Pobiera kontekst dla danego wątku w tym procesie.</span><span class="sxs-lookup"><span data-stu-id="74484-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74484-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="74484-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74484-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="74484-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="74484-106">podczas Identyfikator wątku, dla którego ma zostać pobrany kontekst.</span><span class="sxs-lookup"><span data-stu-id="74484-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="74484-107">podczas Rozmiar `context` tablicy.</span><span class="sxs-lookup"><span data-stu-id="74484-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="74484-108">[in. out] Tablica bajtów opisująca kontekst wątku.</span><span class="sxs-lookup"><span data-stu-id="74484-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="74484-109">Kontekst określa architekturę procesora, w którym wykonywany jest wątek.</span><span class="sxs-lookup"><span data-stu-id="74484-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74484-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="74484-110">Remarks</span></span>  

 <span data-ttu-id="74484-111">Debuger powinien wywołać tę metodę zamiast `GetThreadContext` metody Win32, ponieważ wątek może być w stanie "przejęte", w którym jego kontekst został tymczasowo zmieniony.</span><span class="sxs-lookup"><span data-stu-id="74484-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="74484-112">Ta metoda powinna być używana tylko wtedy, gdy wątek znajduje się w kodzie natywnym.</span><span class="sxs-lookup"><span data-stu-id="74484-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="74484-113">Użyj [ICorDebugRegisterSet](icordebugregisterset-interface.md) dla wątków w kodzie zarządzanym.</span><span class="sxs-lookup"><span data-stu-id="74484-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="74484-114">Zwrócone dane są strukturą kontekstu dla bieżącej platformy.</span><span class="sxs-lookup"><span data-stu-id="74484-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="74484-115">Podobnie jak w przypadku `GetThreadContext` metody Win32, obiekt wywołujący powinien inicjować `context` parametr przed wywołaniem tej metody.</span><span class="sxs-lookup"><span data-stu-id="74484-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74484-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="74484-116">Requirements</span></span>  

 <span data-ttu-id="74484-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74484-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74484-118">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="74484-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74484-119">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="74484-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74484-120">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74484-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
