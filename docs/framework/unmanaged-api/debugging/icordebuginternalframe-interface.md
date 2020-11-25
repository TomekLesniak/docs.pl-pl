---
title: ICorDebugInternalFrame, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
ms.openlocfilehash: b7e738f06f9a9a06caedec2bdd0de4ab57f6d9b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719726"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="744c8-102">ICorDebugInternalFrame, interfejs</span><span class="sxs-lookup"><span data-stu-id="744c8-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="744c8-103">Reprezentuje wewnętrzną ramkę środowiska uruchomieniowego na stosie.</span><span class="sxs-lookup"><span data-stu-id="744c8-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="744c8-104">Ten interfejs jest podklasą interfejsu ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="744c8-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="744c8-105">Metody</span><span class="sxs-lookup"><span data-stu-id="744c8-105">Methods</span></span>  
  
|<span data-ttu-id="744c8-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="744c8-106">Method</span></span>|<span data-ttu-id="744c8-107">Opis</span><span class="sxs-lookup"><span data-stu-id="744c8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="744c8-108">GetFrameType, metoda</span><span class="sxs-lookup"><span data-stu-id="744c8-108">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="744c8-109">Pobiera typ tej wewnętrznej ramki.</span><span class="sxs-lookup"><span data-stu-id="744c8-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="744c8-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="744c8-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="744c8-111">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="744c8-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="744c8-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="744c8-112">Requirements</span></span>  

 <span data-ttu-id="744c8-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="744c8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="744c8-114">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="744c8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="744c8-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="744c8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="744c8-116">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="744c8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="744c8-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="744c8-117">See also</span></span>

- [<span data-ttu-id="744c8-118">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="744c8-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
