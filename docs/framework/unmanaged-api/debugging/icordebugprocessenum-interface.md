---
title: ICorDebugProcessEnum, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum
helpviewer_keywords:
- ICorDebugProcessEnum interface [.NET Framework debugging]
ms.assetid: b63a507a-ca97-4be0-8e4f-401cce2125f6
topic_type:
- apiref
ms.openlocfilehash: 31f26a40294857701b151cd2fce35b061da28238
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732531"
---
# <a name="icordebugprocessenum-interface"></a><span data-ttu-id="229d7-102">ICorDebugProcessEnum, interfejs</span><span class="sxs-lookup"><span data-stu-id="229d7-102">ICorDebugProcessEnum Interface</span></span>

<span data-ttu-id="229d7-103">Implementuje metody ICorDebugEnum i wylicza tablice ICorDebugProcess.</span><span class="sxs-lookup"><span data-stu-id="229d7-103">Implements ICorDebugEnum methods and enumerates ICorDebugProcess arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="229d7-104">Metody</span><span class="sxs-lookup"><span data-stu-id="229d7-104">Methods</span></span>  
  
|<span data-ttu-id="229d7-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="229d7-105">Method</span></span>|<span data-ttu-id="229d7-106">Opis</span><span class="sxs-lookup"><span data-stu-id="229d7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="229d7-107">Next, metoda</span><span class="sxs-lookup"><span data-stu-id="229d7-107">Next Method</span></span>](icordebugprocessenum-next-method.md)|<span data-ttu-id="229d7-108">Pobiera określoną liczbę `ICorDebugProcess` wystąpień z wyliczenia, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="229d7-108">Gets the specified number of `ICorDebugProcess` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="229d7-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="229d7-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="229d7-110">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="229d7-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="229d7-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="229d7-111">Requirements</span></span>  

 <span data-ttu-id="229d7-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="229d7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="229d7-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="229d7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="229d7-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="229d7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="229d7-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="229d7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="229d7-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="229d7-116">See also</span></span>

- [<span data-ttu-id="229d7-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="229d7-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
