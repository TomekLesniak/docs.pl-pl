---
title: 'ICorDebugModuleDebugEvent:: GetModule — Metoda'
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: ec23cda02ff689a3365fe96fb5280054a9795caa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709508"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="e6e54-102">ICorDebugModuleDebugEvent:: GetModule — Metoda</span><span class="sxs-lookup"><span data-stu-id="e6e54-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>

<span data-ttu-id="e6e54-103">Pobiera scalony moduł, który został właśnie załadowany lub zwolniony.</span><span class="sxs-lookup"><span data-stu-id="e6e54-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6e54-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e6e54-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6e54-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e6e54-105">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="e6e54-106">określoną Wskaźnik do adresu obiektu ICorDebugModule, który reprezentuje scalony moduł, który został właśnie załadowany lub zwolniony.</span><span class="sxs-lookup"><span data-stu-id="e6e54-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6e54-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e6e54-107">Remarks</span></span>  

 <span data-ttu-id="e6e54-108">Można wywołać metodę [GetEventKind](icordebugdebugevent-geteventkind-method.md) , aby określić, czy moduł został załadowany, czy zwolniony.</span><span class="sxs-lookup"><span data-stu-id="e6e54-108">You can call the [GetEventKind](icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6e54-109">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e6e54-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6e54-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e6e54-110">Requirements</span></span>  

 <span data-ttu-id="e6e54-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6e54-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6e54-112">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e6e54-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6e54-113">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e6e54-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6e54-114">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6e54-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6e54-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e6e54-115">See also</span></span>

- [<span data-ttu-id="e6e54-116">ICorDebugModuleDebugEvent, interfejs</span><span class="sxs-lookup"><span data-stu-id="e6e54-116">ICorDebugModuleDebugEvent Interface</span></span>](icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="e6e54-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="e6e54-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
