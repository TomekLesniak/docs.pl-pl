---
title: ICorDebugModuleEnum, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
ms.openlocfilehash: 08d16393a04888cd3f1a03fa209a1fceac28520b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724757"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="af188-102">ICorDebugModuleEnum, interfejs</span><span class="sxs-lookup"><span data-stu-id="af188-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="af188-103">Implementuje metody ICorDebugEnum i wylicza tablice ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="af188-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af188-104">Metody</span><span class="sxs-lookup"><span data-stu-id="af188-104">Methods</span></span>  
  
|<span data-ttu-id="af188-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="af188-105">Method</span></span>|<span data-ttu-id="af188-106">Opis</span><span class="sxs-lookup"><span data-stu-id="af188-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af188-107">Next, metoda</span><span class="sxs-lookup"><span data-stu-id="af188-107">Next Method</span></span>](icordebugmoduleenum-next-method.md)|<span data-ttu-id="af188-108">Pobiera określoną liczbę `ICorDebugModule` wystąpień z wyliczenia, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="af188-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af188-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="af188-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af188-110">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="af188-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af188-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="af188-111">Requirements</span></span>  

 <span data-ttu-id="af188-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af188-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af188-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="af188-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af188-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="af188-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af188-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af188-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af188-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="af188-116">See also</span></span>

- [<span data-ttu-id="af188-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="af188-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
