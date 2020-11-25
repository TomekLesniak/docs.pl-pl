---
title: ICorDebugObjectEnum, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
ms.openlocfilehash: 9400c4fa3ddcefef923d7bcfaae80e2cef62dc7d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695468"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="afa8e-102">ICorDebugObjectEnum, interfejs</span><span class="sxs-lookup"><span data-stu-id="afa8e-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="afa8e-103">Implementuje metody ICorDebugEnum i wylicza tablice obiektów według ich względnych adresów wirtualnych (RVA).</span><span class="sxs-lookup"><span data-stu-id="afa8e-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="afa8e-104">Metody</span><span class="sxs-lookup"><span data-stu-id="afa8e-104">Methods</span></span>  
  
|<span data-ttu-id="afa8e-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="afa8e-105">Method</span></span>|<span data-ttu-id="afa8e-106">Opis</span><span class="sxs-lookup"><span data-stu-id="afa8e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="afa8e-107">Next, metoda</span><span class="sxs-lookup"><span data-stu-id="afa8e-107">Next Method</span></span>](icordebugobjectenum-next-method.md)|<span data-ttu-id="afa8e-108">Pobiera RVA określoną liczbę obiektów z wyliczenia, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="afa8e-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afa8e-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="afa8e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="afa8e-110">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="afa8e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afa8e-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="afa8e-111">Requirements</span></span>  

 <span data-ttu-id="afa8e-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afa8e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afa8e-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="afa8e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afa8e-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="afa8e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afa8e-115">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afa8e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa8e-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="afa8e-116">See also</span></span>

- [<span data-ttu-id="afa8e-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="afa8e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
