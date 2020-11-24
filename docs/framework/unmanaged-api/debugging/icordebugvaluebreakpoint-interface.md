---
title: ICorDebugValueBreakpoint, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
ms.openlocfilehash: cf0a87afd1c0057c054205432fea7aa5844afb53
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684416"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="1fadf-102">ICorDebugValueBreakpoint, interfejs</span><span class="sxs-lookup"><span data-stu-id="1fadf-102">ICorDebugValueBreakpoint Interface</span></span>

<span data-ttu-id="1fadf-103">Rozszerza interfejs ICorDebugBreakpoint w celu zapewnienia dostępu do określonych wartości.</span><span class="sxs-lookup"><span data-stu-id="1fadf-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1fadf-104">Metody</span><span class="sxs-lookup"><span data-stu-id="1fadf-104">Methods</span></span>  
  
|<span data-ttu-id="1fadf-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="1fadf-105">Method</span></span>|<span data-ttu-id="1fadf-106">Opis</span><span class="sxs-lookup"><span data-stu-id="1fadf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1fadf-107">GetValue — Metoda</span><span class="sxs-lookup"><span data-stu-id="1fadf-107">GetValue Method</span></span>](icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="1fadf-108">Pobiera wskaźnik interfejsu do obiektu ICorDebugValue, który reprezentuje wartość obiektu, na którym jest ustawiony punkt przerwania.</span><span class="sxs-lookup"><span data-stu-id="1fadf-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fadf-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1fadf-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1fadf-110">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="1fadf-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fadf-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1fadf-111">Requirements</span></span>  

 <span data-ttu-id="1fadf-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fadf-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fadf-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="1fadf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fadf-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="1fadf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fadf-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fadf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fadf-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1fadf-116">See also</span></span>

- [<span data-ttu-id="1fadf-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="1fadf-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
