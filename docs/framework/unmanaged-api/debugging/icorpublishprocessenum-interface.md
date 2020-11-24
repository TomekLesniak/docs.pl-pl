---
title: ICorPublishProcessEnum — Interfejs
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: ebf484524b32d8e917d88c21425fab314dfc41be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692621"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="2423a-102">ICorPublishProcessEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2423a-102">ICorPublishProcessEnum Interface</span></span>

<span data-ttu-id="2423a-103">Podklasa interfejsu [ICorPublishEnum](icorpublishenum-interface.md) , która dostarcza metody umożliwiające przechodzenie kolekcji obiektów [ICorPublishProcess](icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2423a-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2423a-104">Metody</span><span class="sxs-lookup"><span data-stu-id="2423a-104">Methods</span></span>  
  
|<span data-ttu-id="2423a-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="2423a-105">Method</span></span>|<span data-ttu-id="2423a-106">Opis</span><span class="sxs-lookup"><span data-stu-id="2423a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2423a-107">Next, metoda</span><span class="sxs-lookup"><span data-stu-id="2423a-107">Next Method</span></span>](icorpublishprocessenum-next-method.md)|<span data-ttu-id="2423a-108">Pobiera określoną liczbę `ICorPublishProcess` wystąpień z kolekcji, rozpoczynając od bieżącego położenia.</span><span class="sxs-lookup"><span data-stu-id="2423a-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2423a-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2423a-109">Remarks</span></span>  

 <span data-ttu-id="2423a-110">`ICorPublishProcessEnum`Interfejs implementuje metody interfejsu abstrakcyjnego, [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2423a-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="2423a-111">`ICorPublishProcessEnum`Wystąpienie jest tworzone przez metodę [ICorPublish:: EnumProcesses —](icorpublish-enumprocesses-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2423a-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="2423a-112">Przechodzenie kolekcji `ICorPublishProcess` obiektów jest oparte na kryteriach filtrowania określonych w momencie `ICorPublishProcessEnum` utworzenia wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="2423a-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2423a-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2423a-113">Requirements</span></span>  

 <span data-ttu-id="2423a-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2423a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2423a-115">**Nagłówek:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="2423a-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2423a-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2423a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2423a-117">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2423a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2423a-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2423a-118">See also</span></span>

- [<span data-ttu-id="2423a-119">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="2423a-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2423a-120">CorpubPublish — Klasa coclass</span><span class="sxs-lookup"><span data-stu-id="2423a-120">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
