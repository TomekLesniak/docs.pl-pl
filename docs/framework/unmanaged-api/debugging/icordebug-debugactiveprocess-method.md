---
title: ICorDebug::DebugActiveProcess — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 1713623fa575bea6df649106b37212f7aeaee6db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723470"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="acb5b-102">ICorDebug::DebugActiveProcess — Metoda</span><span class="sxs-lookup"><span data-stu-id="acb5b-102">ICorDebug::DebugActiveProcess Method</span></span>

<span data-ttu-id="acb5b-103">Dołącza debuger do istniejącego procesu.</span><span class="sxs-lookup"><span data-stu-id="acb5b-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acb5b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="acb5b-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acb5b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="acb5b-105">Parameters</span></span>  

 `id`  
 <span data-ttu-id="acb5b-106">podczas Identyfikator procesu, do którego ma zostać dołączony debuger.</span><span class="sxs-lookup"><span data-stu-id="acb5b-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="acb5b-107">podczas Wartość logiczna, która jest ustawiona na, `true` Jeśli debuger powinien zachowywać się jako debuger Win32 dla procesu i wysyłał niezarządzane wywołania zwrotne; w przeciwnym razie `false` .</span><span class="sxs-lookup"><span data-stu-id="acb5b-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="acb5b-108">określoną Wskaźnik do adresu obiektu "ICorDebugProcess", który reprezentuje proces, do którego został podłączony debuger.</span><span class="sxs-lookup"><span data-stu-id="acb5b-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acb5b-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="acb5b-109">Remarks</span></span>  

 <span data-ttu-id="acb5b-110">Debugowanie międzyoperacyjności nie jest obsługiwane na platformach Win9x i innych niż x86, na przykład na platformach opartych na architekturze IA-64 i AMD64.</span><span class="sxs-lookup"><span data-stu-id="acb5b-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acb5b-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="acb5b-111">Requirements</span></span>  

 <span data-ttu-id="acb5b-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acb5b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acb5b-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="acb5b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acb5b-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="acb5b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acb5b-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acb5b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb5b-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="acb5b-116">See also</span></span>

- [<span data-ttu-id="acb5b-117">ICorDebug — Interfejs</span><span class="sxs-lookup"><span data-stu-id="acb5b-117">ICorDebug Interface</span></span>](icordebug-interface.md)
