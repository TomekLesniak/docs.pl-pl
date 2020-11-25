---
title: ICorDebugMetaDataLocator — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator
helpviewer_keywords:
- ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: 287f5ecd-863f-4090-a615-077859f0257b
topic_type:
- apiref
ms.openlocfilehash: dbf5c751e84dfd9bf0549e8ce79d07a90fb4a3b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710392"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="178c9-102">ICorDebugMetaDataLocator — Interfejs</span><span class="sxs-lookup"><span data-stu-id="178c9-102">ICorDebugMetaDataLocator Interface</span></span>

<span data-ttu-id="178c9-103">Dostarcza informacje o metadanych do debugera.</span><span class="sxs-lookup"><span data-stu-id="178c9-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="178c9-104">Metody</span><span class="sxs-lookup"><span data-stu-id="178c9-104">Methods</span></span>  
  
|<span data-ttu-id="178c9-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="178c9-105">Method</span></span>|<span data-ttu-id="178c9-106">Opis</span><span class="sxs-lookup"><span data-stu-id="178c9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="178c9-107">GetMetaData, metoda</span><span class="sxs-lookup"><span data-stu-id="178c9-107">GetMetaData Method</span></span>](icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="178c9-108">Prosi debugera o zwrócenie pełnej ścieżki do modułu, którego metadane są wymagane do ukończenia operacji wymaganej przez debuger.</span><span class="sxs-lookup"><span data-stu-id="178c9-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="178c9-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="178c9-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="178c9-110">Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.</span><span class="sxs-lookup"><span data-stu-id="178c9-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="178c9-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="178c9-111">Requirements</span></span>  

 <span data-ttu-id="178c9-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="178c9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="178c9-113">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="178c9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="178c9-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="178c9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="178c9-115">**.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="178c9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="178c9-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="178c9-116">See also</span></span>

- [<span data-ttu-id="178c9-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="178c9-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="178c9-118">Debugowanie</span><span class="sxs-lookup"><span data-stu-id="178c9-118">Debugging</span></span>](index.md)
