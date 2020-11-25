---
title: ICorDebugILFrame2, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
ms.openlocfilehash: 3ada9e19bb1a92b3bd7e41340b99bf81b651dd37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725017"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="cbd27-102">ICorDebugILFrame2, interfejs</span><span class="sxs-lookup"><span data-stu-id="cbd27-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="cbd27-103">Logiczne rozszerzenie interfejsu ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="cbd27-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cbd27-104">Metody</span><span class="sxs-lookup"><span data-stu-id="cbd27-104">Methods</span></span>  
  
|<span data-ttu-id="cbd27-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="cbd27-105">Method</span></span>|<span data-ttu-id="cbd27-106">Opis</span><span class="sxs-lookup"><span data-stu-id="cbd27-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cbd27-107">EnumerateTypeParameters, metoda</span><span class="sxs-lookup"><span data-stu-id="cbd27-107">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="cbd27-108">Pobiera obiekt ICorDebugTypeEnum, który zawiera <xref:System.Type> Parametry w tej ramce.</span><span class="sxs-lookup"><span data-stu-id="cbd27-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="cbd27-109">RemapFunction, metoda</span><span class="sxs-lookup"><span data-stu-id="cbd27-109">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="cbd27-110">Ponownie mapuje edytowaną funkcję przez określenie nowego przesunięcia MSIL.</span><span class="sxs-lookup"><span data-stu-id="cbd27-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbd27-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cbd27-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cbd27-112">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="cbd27-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbd27-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="cbd27-113">Requirements</span></span>  

 <span data-ttu-id="cbd27-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbd27-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbd27-115">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="cbd27-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbd27-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="cbd27-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbd27-117">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbd27-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbd27-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="cbd27-118">See also</span></span>

- [<span data-ttu-id="cbd27-119">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="cbd27-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
