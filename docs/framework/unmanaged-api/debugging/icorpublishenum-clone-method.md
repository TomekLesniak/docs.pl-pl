---
title: ICorPublishEnum::Clone — Metoda
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
ms.openlocfilehash: 44ecba99999d04603477f411e68834548f6a7cda
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693557"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="0524d-102">ICorPublishEnum::Clone — Metoda</span><span class="sxs-lookup"><span data-stu-id="0524d-102">ICorPublishEnum::Clone Method</span></span>

<span data-ttu-id="0524d-103">Tworzy kopię tego obiektu [ICorPublishEnum](icorpublishenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0524d-103">Creates a copy of this [ICorPublishEnum](icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0524d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0524d-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0524d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="0524d-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="0524d-106">określoną Wskaźnik do adresu `ICorPublishEnum` obiektu, który jest kopią tego `ICorPublishEnum` obiektu.</span><span class="sxs-lookup"><span data-stu-id="0524d-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0524d-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="0524d-107">Requirements</span></span>  

 <span data-ttu-id="0524d-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0524d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0524d-109">**Nagłówek:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="0524d-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0524d-110">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0524d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0524d-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0524d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0524d-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0524d-112">See also</span></span>

- [<span data-ttu-id="0524d-113">ICorPublishEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="0524d-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
