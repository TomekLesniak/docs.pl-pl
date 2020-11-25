---
title: 'ICorDebugMutableDataTarget:: SetThreadContext —, Metoda'
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 558a1ee2eb0ac06213c2ebcebbd5595b69ecc43e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695713"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="63ace-102">ICorDebugMutableDataTarget:: SetThreadContext —, Metoda</span><span class="sxs-lookup"><span data-stu-id="63ace-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>

<span data-ttu-id="63ace-103">Ustawia kontekst (wartości rejestru) dla wątku.</span><span class="sxs-lookup"><span data-stu-id="63ace-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ace-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="63ace-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63ace-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="63ace-105">Parameters</span></span>  

 `dwThreadID`  
 <span data-ttu-id="63ace-106">podczas Identyfikator wątku zdefiniowanego przez system operacyjny.</span><span class="sxs-lookup"><span data-stu-id="63ace-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="63ace-107">podczas Rozmiar `pContext` buforu, który ma zostać zapisany.</span><span class="sxs-lookup"><span data-stu-id="63ace-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="63ace-108">podczas Wskaźnik do bajtów do zapisania.</span><span class="sxs-lookup"><span data-stu-id="63ace-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63ace-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="63ace-109">Remarks</span></span>  

 <span data-ttu-id="63ace-110">`SetThreadContext`Metoda aktualizuje bieżący kontekst dla wątku określonego przez argument zdefiniowany przez system operacyjny `dwThreadID` .</span><span class="sxs-lookup"><span data-stu-id="63ace-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="63ace-111">Format rekordu kontekstu jest określany przez platformę wskazywaną przez metodę [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="63ace-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="63ace-112">W systemie Windows jest to struktura [kontekstu](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .</span><span class="sxs-lookup"><span data-stu-id="63ace-112">On Windows, this is a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63ace-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="63ace-113">Requirements</span></span>  

 <span data-ttu-id="63ace-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63ace-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63ace-115">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="63ace-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63ace-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="63ace-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63ace-117">**.NET Framework wersje:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63ace-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ace-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="63ace-118">See also</span></span>

- [<span data-ttu-id="63ace-119">ICorDebugMutableDataTarget, interfejs</span><span class="sxs-lookup"><span data-stu-id="63ace-119">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="63ace-120">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="63ace-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
