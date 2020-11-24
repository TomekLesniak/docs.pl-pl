---
title: ICorPublishProcess — Interfejs
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
ms.openlocfilehash: 8ee59e9d416d1c53312e4fccb6953f20b03b29b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693089"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="c5021-102">ICorPublishProcess — Interfejs</span><span class="sxs-lookup"><span data-stu-id="c5021-102">ICorPublishProcess Interface</span></span>

<span data-ttu-id="c5021-103">Dostarcza metody, które mają dostęp do informacji o procesie.</span><span class="sxs-lookup"><span data-stu-id="c5021-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c5021-104">Metody</span><span class="sxs-lookup"><span data-stu-id="c5021-104">Methods</span></span>  
  
|<span data-ttu-id="c5021-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="c5021-105">Method</span></span>|<span data-ttu-id="c5021-106">Opis</span><span class="sxs-lookup"><span data-stu-id="c5021-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c5021-107">EnumAppDomains, metoda</span><span class="sxs-lookup"><span data-stu-id="c5021-107">EnumAppDomains Method</span></span>](icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="c5021-108">Pobiera wystąpienie [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) , które zawiera domeny aplikacji w procesie, do którego się odwołuje `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="c5021-108">Gets an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="c5021-109">GetDisplayName — Metoda</span><span class="sxs-lookup"><span data-stu-id="c5021-109">GetDisplayName Method</span></span>](icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="c5021-110">Pobiera pełną ścieżkę pliku wykonywalnego dla procesu, do którego się odwołuje `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="c5021-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="c5021-111">GetProcessID, metoda</span><span class="sxs-lookup"><span data-stu-id="c5021-111">GetProcessID Method</span></span>](icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="c5021-112">Pobiera identyfikator systemu operacyjnego dla procesu, do którego się odwołuje `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="c5021-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="c5021-113">IsManaged, metoda</span><span class="sxs-lookup"><span data-stu-id="c5021-113">IsManaged Method</span></span>](icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="c5021-114">Pobiera wartość wskazującą, czy proces, do którego się odwołuje, `ICorPublishProcess` jest znany jako uruchomiony kod zarządzany.</span><span class="sxs-lookup"><span data-stu-id="c5021-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5021-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c5021-115">Requirements</span></span>  

 <span data-ttu-id="c5021-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5021-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5021-117">**Nagłówek:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="c5021-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c5021-118">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c5021-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5021-119">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5021-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5021-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c5021-120">See also</span></span>

- [<span data-ttu-id="c5021-121">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="c5021-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c5021-122">CorpubPublish — Klasa coclass</span><span class="sxs-lookup"><span data-stu-id="c5021-122">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
