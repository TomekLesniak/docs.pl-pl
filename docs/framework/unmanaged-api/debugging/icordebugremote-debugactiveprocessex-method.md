---
title: ICorDebugRemote::DebugActiveProcessEx — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
ms.openlocfilehash: c9847fd6122aa32c95aecd5643a62a6775ae38d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712121"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="27dbb-102">ICorDebugRemote::DebugActiveProcessEx — Metoda</span><span class="sxs-lookup"><span data-stu-id="27dbb-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>

<span data-ttu-id="27dbb-103">Uruchamia proces na maszynie zdalnej pod debugerem.</span><span class="sxs-lookup"><span data-stu-id="27dbb-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27dbb-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="27dbb-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27dbb-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="27dbb-105">Parameters</span></span>  

 `pRemoteTarget`  
 <span data-ttu-id="27dbb-106">podczas Wskaźnik do [interfejsu ICorDebugRemoteTarget](icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="27dbb-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="27dbb-107">Ten parametr służy do określania komputera, na którym jest uruchomiony proces.</span><span class="sxs-lookup"><span data-stu-id="27dbb-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="27dbb-108">podczas Identyfikator procesu, do którego ma zostać dołączony debuger.</span><span class="sxs-lookup"><span data-stu-id="27dbb-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="27dbb-109">[w] `true` Jeśli debuger powinien działać jako debuger Win32 dla procesu i wysyłać niezarządzane wywołania zwrotne; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="27dbb-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="27dbb-110">określoną Wskaźnik do adresu obiektu "ICorDebugProcess", który reprezentuje proces, do którego został podłączony debuger.</span><span class="sxs-lookup"><span data-stu-id="27dbb-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27dbb-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="27dbb-111">Return Value</span></span>  

 <span data-ttu-id="27dbb-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="27dbb-112">S_OK</span></span>  
 <span data-ttu-id="27dbb-113">Pomyślnie dołączono do procesu na komputerze zdalnym.</span><span class="sxs-lookup"><span data-stu-id="27dbb-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="27dbb-114">E_FAIL (lub inne kody powrotne E_)</span><span class="sxs-lookup"><span data-stu-id="27dbb-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="27dbb-115">Nie można dołączyć do procesu na komputerze zdalnym.</span><span class="sxs-lookup"><span data-stu-id="27dbb-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27dbb-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="27dbb-116">Remarks</span></span>  

 <span data-ttu-id="27dbb-117">Debugowanie w trybie mieszanym nie jest obsługiwane w programie Silverlight.</span><span class="sxs-lookup"><span data-stu-id="27dbb-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27dbb-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="27dbb-118">Requirements</span></span>  

 <span data-ttu-id="27dbb-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27dbb-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27dbb-120">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="27dbb-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27dbb-121">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="27dbb-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27dbb-122">**.NET Framework wersje:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="27dbb-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27dbb-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="27dbb-123">See also</span></span>

- [<span data-ttu-id="27dbb-124">ICorDebugRemote — Interfejs</span><span class="sxs-lookup"><span data-stu-id="27dbb-124">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="27dbb-125">ICorDebug — Interfejs</span><span class="sxs-lookup"><span data-stu-id="27dbb-125">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="27dbb-126">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="27dbb-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
