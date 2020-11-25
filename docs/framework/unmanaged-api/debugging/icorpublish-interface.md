---
title: ICorPublish — Interfejs
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
ms.openlocfilehash: 3ff4efe8b3e2932da7f65246bf4ad614a4dd86cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694415"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="0eaae-102">ICorPublish — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0eaae-102">ICorPublish Interface</span></span>

<span data-ttu-id="0eaae-103">Służy jako ogólny interfejs publikowania informacji o procesach i informacjach o domenach aplikacji w tych procesach.</span><span class="sxs-lookup"><span data-stu-id="0eaae-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0eaae-104">Metody</span><span class="sxs-lookup"><span data-stu-id="0eaae-104">Methods</span></span>  
  
|<span data-ttu-id="0eaae-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="0eaae-105">Method</span></span>|<span data-ttu-id="0eaae-106">Opis</span><span class="sxs-lookup"><span data-stu-id="0eaae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0eaae-107">EnumProcesses, metoda</span><span class="sxs-lookup"><span data-stu-id="0eaae-107">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="0eaae-108">Pobiera wystąpienie [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) , które zawiera zarządzane procesy uruchomione na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="0eaae-108">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="0eaae-109">GetProcess — Metoda</span><span class="sxs-lookup"><span data-stu-id="0eaae-109">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="0eaae-110">Pobiera wystąpienie [ICorPublishProcess](icorpublishprocess-interface.md) , które reprezentuje proces o określonym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="0eaae-110">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0eaae-111">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0eaae-111">Requirements</span></span>  

 <span data-ttu-id="0eaae-112">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0eaae-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eaae-113">**Nagłówek:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="0eaae-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0eaae-114">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0eaae-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0eaae-115">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eaae-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eaae-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0eaae-116">See also</span></span>

- [<span data-ttu-id="0eaae-117">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="0eaae-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0eaae-118">CorpubPublish — Klasa coclass</span><span class="sxs-lookup"><span data-stu-id="0eaae-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
