---
title: 'ICorDebugExceptionDebugEvent:: GetFlags — Metoda'
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 02a20b54b7fecc711bda010c6916fe036cf20dd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729606"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="999fa-102">ICorDebugExceptionDebugEvent:: GetFlags — Metoda</span><span class="sxs-lookup"><span data-stu-id="999fa-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>

<span data-ttu-id="999fa-103">Pobiera flagę wskazującą, czy wyjątek może być przechwytywany.</span><span class="sxs-lookup"><span data-stu-id="999fa-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="999fa-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="999fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="999fa-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="999fa-105">Parameters</span></span>  

 `pdwFlags`  
 <span data-ttu-id="999fa-106">określoną Wskaźnik do wartości [CorDebugExceptionFlags —](cordebugexceptionflags-enumeration.md) , który wskazuje, czy można przechwycić wyjątek.</span><span class="sxs-lookup"><span data-stu-id="999fa-106">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="999fa-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="999fa-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="999fa-108">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="999fa-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="999fa-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="999fa-109">Requirements</span></span>  

 <span data-ttu-id="999fa-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="999fa-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="999fa-111">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="999fa-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="999fa-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="999fa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="999fa-113">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="999fa-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="999fa-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="999fa-114">See also</span></span>

- [<span data-ttu-id="999fa-115">Interfejs ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="999fa-115">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="999fa-116">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="999fa-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
