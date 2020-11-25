---
title: ICorDebugAssemblyEnum, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum
helpviewer_keywords:
- ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: 891ceb43-5161-421e-a0bf-299962fd7efd
topic_type:
- apiref
ms.openlocfilehash: dea5c0fd5d4ed1f830d9e75097d49c544dac2e57
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719251"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="71389-102">ICorDebugAssemblyEnum, interfejs</span><span class="sxs-lookup"><span data-stu-id="71389-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="71389-103">Implementuje metody ICorDebugEnum i wylicza tablice ICorDebugAssembly.</span><span class="sxs-lookup"><span data-stu-id="71389-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="71389-104">Metody</span><span class="sxs-lookup"><span data-stu-id="71389-104">Methods</span></span>  
  
|<span data-ttu-id="71389-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="71389-105">Method</span></span>|<span data-ttu-id="71389-106">Opis</span><span class="sxs-lookup"><span data-stu-id="71389-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="71389-107">Next, metoda</span><span class="sxs-lookup"><span data-stu-id="71389-107">Next Method</span></span>](icordebugassemblyenum-next-method.md)|<span data-ttu-id="71389-108">Pobiera określoną liczbę `ICorDebugAssembly` wystąpień w wyliczeniu, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="71389-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71389-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="71389-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71389-110">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="71389-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71389-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="71389-111">Requirements</span></span>  

 <span data-ttu-id="71389-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71389-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71389-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="71389-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71389-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="71389-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71389-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71389-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71389-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="71389-116">See also</span></span>

- [<span data-ttu-id="71389-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="71389-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
