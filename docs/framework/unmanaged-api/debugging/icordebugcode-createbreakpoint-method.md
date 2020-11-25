---
title: ICorDebugCode::CreateBreakpoint — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
ms.openlocfilehash: ade428ce001a6b40e2fed67f4f23b12cef5ea30f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717659"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="24102-102">ICorDebugCode::CreateBreakpoint — Metoda</span><span class="sxs-lookup"><span data-stu-id="24102-102">ICorDebugCode::CreateBreakpoint Method</span></span>

<span data-ttu-id="24102-103">Tworzy punkt przerwania w tym segmencie kodu w określonym przesunięciu.</span><span class="sxs-lookup"><span data-stu-id="24102-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24102-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="24102-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24102-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="24102-105">Parameters</span></span>  

 `offset`  
 <span data-ttu-id="24102-106">podczas Przesunięcie, od którego ma zostać utworzony punkt przerwania.</span><span class="sxs-lookup"><span data-stu-id="24102-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="24102-107">określoną Wskaźnik do adresu obiektu "ICorDebugFunctionBreakpoint", który reprezentuje punkt przerwania.</span><span class="sxs-lookup"><span data-stu-id="24102-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24102-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="24102-108">Remarks</span></span>  

 <span data-ttu-id="24102-109">Przed aktywnym punktem przerwania należy dodać go do obiektu procesu.</span><span class="sxs-lookup"><span data-stu-id="24102-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="24102-110">Jeśli ten kod jest kodem języka pośredniego (MSIL) firmy Microsoft, a istnieje skompilowana, natywna wersja kodu, punkt przerwania zostanie zastosowany w kodzie skompilowanym JIT.</span><span class="sxs-lookup"><span data-stu-id="24102-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="24102-111">(To samo jest prawdziwe, jeśli kod jest kompilowany w trybie JIT później).</span><span class="sxs-lookup"><span data-stu-id="24102-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24102-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="24102-112">Requirements</span></span>  

 <span data-ttu-id="24102-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24102-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24102-114">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="24102-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24102-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="24102-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24102-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24102-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
