---
title: ICorDebugStepper2, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2
helpviewer_keywords:
- ICorDebugStepper2 interface [.NET Framework debugging]
ms.assetid: 7a191c2a-95ea-4d47-83b0-44de2b632d63
topic_type:
- apiref
ms.openlocfilehash: ecbedfbca37a3630fc6d40c173f8a6cd05b4d3fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727643"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="5588d-102">ICorDebugStepper2, interfejs</span><span class="sxs-lookup"><span data-stu-id="5588d-102">ICorDebugStepper2 Interface</span></span>

<span data-ttu-id="5588d-103">Zapewnia obsługę debugowania tylko mój kod (JMC).</span><span class="sxs-lookup"><span data-stu-id="5588d-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5588d-104">Metody</span><span class="sxs-lookup"><span data-stu-id="5588d-104">Methods</span></span>  
  
|<span data-ttu-id="5588d-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="5588d-105">Method</span></span>|<span data-ttu-id="5588d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="5588d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5588d-107">SetJMC, metoda</span><span class="sxs-lookup"><span data-stu-id="5588d-107">SetJMC Method</span></span>](icordebugstepper2-setjmc-method.md)|<span data-ttu-id="5588d-108">Ustawia wartość określającą, czy ten ICorDebugStepper czynności tylko za pomocą kodu, który jest tworzony przez dewelopera aplikacji.</span><span class="sxs-lookup"><span data-stu-id="5588d-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5588d-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5588d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5588d-110">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="5588d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5588d-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5588d-111">Requirements</span></span>  

 <span data-ttu-id="5588d-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5588d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5588d-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5588d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5588d-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5588d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5588d-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5588d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5588d-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5588d-116">See also</span></span>

- [<span data-ttu-id="5588d-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="5588d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
