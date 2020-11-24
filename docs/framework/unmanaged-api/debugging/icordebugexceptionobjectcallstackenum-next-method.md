---
title: ICorDebugExceptionObjectCallStackEnum::Next — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
ms.openlocfilehash: 17d5367564ec1ec98efc264ad9a5794c0d04a947
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672139"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a><span data-ttu-id="f2cb5-102">ICorDebugExceptionObjectCallStackEnum::Next — Metoda</span><span class="sxs-lookup"><span data-stu-id="f2cb5-102">ICorDebugExceptionObjectCallStackEnum::Next Method</span></span>

<span data-ttu-id="f2cb5-103">Pobiera określoną liczbę wystąpień [CorDebugExceptionObjectStackFrame —](cordebugexceptionobjectstackframe-structure.md) , które zawierają informacje z stosu wywołań obiektu wyjątku.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-103">Gets the specified number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances that contain information from an exception object's call stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2cb5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="f2cb5-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2cb5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="f2cb5-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="f2cb5-106">podczas Liczba wystąpień [CorDebugExceptionObjectStackFrame —](cordebugexceptionobjectstackframe-structure.md) do pobrania.</span><span class="sxs-lookup"><span data-stu-id="f2cb5-106">[in] The number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="f2cb5-107">określoną Tablica wskaźników, z których każdy wskazuje obiekt [CorDebugExceptionObjectStackFrame —](cordebugexceptionobjectstackframe-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="f2cb5-107">[out] An array of pointers, each of which points to a [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f2cb5-108">określoną Wskaźnik do liczby zwróconych wystąpień [CorDebugExceptionObjectStackFrame —](cordebugexceptionobjectstackframe-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="f2cb5-108">[out] A pointer to the number of [CorDebugExceptionObjectStackFrame](cordebugexceptionobjectstackframe-structure.md) instances actually returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2cb5-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f2cb5-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2cb5-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="f2cb5-110">Requirements</span></span>  

 <span data-ttu-id="f2cb5-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2cb5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2cb5-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f2cb5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2cb5-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f2cb5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2cb5-114">**.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2cb5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2cb5-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f2cb5-115">See also</span></span>

- [<span data-ttu-id="f2cb5-116">ICorDebugExceptionObjectCallStackEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="f2cb5-116">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](icordebugexceptionobjectcallstackenum-interface.md)
- [<span data-ttu-id="f2cb5-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="f2cb5-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
