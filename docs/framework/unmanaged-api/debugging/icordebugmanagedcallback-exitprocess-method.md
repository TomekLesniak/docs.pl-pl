---
title: ICorDebugManagedCallback::ExitProcess — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
ms.openlocfilehash: 67f3e63b58e08a4b9ccfbd555e6edcdef0d00d90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688977"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="6cb00-102">ICorDebugManagedCallback::ExitProcess — Metoda</span><span class="sxs-lookup"><span data-stu-id="6cb00-102">ICorDebugManagedCallback::ExitProcess Method</span></span>

<span data-ttu-id="6cb00-103">Powiadamia debugera o zakończeniu procesu.</span><span class="sxs-lookup"><span data-stu-id="6cb00-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cb00-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="6cb00-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cb00-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="6cb00-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="6cb00-106">podczas Wskaźnik do obiektu ICorDebugProcess, który reprezentuje proces.</span><span class="sxs-lookup"><span data-stu-id="6cb00-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6cb00-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6cb00-107">Remarks</span></span>  

 <span data-ttu-id="6cb00-108">Nie można kontynuować ze `ExitProcess` zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="6cb00-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="6cb00-109">To zdarzenie może być wyzwalane asynchronicznie do innych zdarzeń, gdy proces zostanie zatrzymany.</span><span class="sxs-lookup"><span data-stu-id="6cb00-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="6cb00-110">Taka sytuacja może wystąpić, jeśli proces kończy się niepomyślnie, zazwyczaj z powodu pewnej siły zewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="6cb00-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="6cb00-111">Jeśli środowisko uruchomieniowe języka wspólnego (CLR) już wysłało zarządzane wywołanie zwrotne, to zdarzenie zostanie opóźnione do momentu zwrócenia tego wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="6cb00-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="6cb00-112">`ExitProcess`Zdarzenie jest jedynym zdarzeniem wyjścia/zwalniania, które ma zostać wywołane podczas zamykania.</span><span class="sxs-lookup"><span data-stu-id="6cb00-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cb00-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="6cb00-113">Requirements</span></span>  

 <span data-ttu-id="6cb00-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6cb00-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cb00-115">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="6cb00-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6cb00-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6cb00-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6cb00-117">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cb00-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cb00-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="6cb00-118">See also</span></span>

- [<span data-ttu-id="6cb00-119">ICorDebugManagedCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="6cb00-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
