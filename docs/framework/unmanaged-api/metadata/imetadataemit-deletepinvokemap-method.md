---
title: IMetaDataEmit::DeletePinvokeMap — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
ms.openlocfilehash: 6fc6cf9b7333dd4caad3c5a4b081fecb060c8f86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722092"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="ddd3f-102">IMetaDataEmit::DeletePinvokeMap — Metoda</span><span class="sxs-lookup"><span data-stu-id="ddd3f-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>

<span data-ttu-id="ddd3f-103">Niszczy metadane mapowania PInvoke dla obiektu, do którego odwołuje się określony token.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddd3f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ddd3f-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddd3f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ddd3f-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="ddd3f-106">podczas `mdFieldDef` Token lub `mdMethodDef` reprezentujący obiekt, dla którego mają zostać usunięte metadane mapowania PInvoke.</span><span class="sxs-lookup"><span data-stu-id="ddd3f-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddd3f-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ddd3f-107">Requirements</span></span>  

 <span data-ttu-id="ddd3f-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddd3f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddd3f-109">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ddd3f-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ddd3f-110">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ddd3f-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ddd3f-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddd3f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddd3f-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ddd3f-112">See also</span></span>

- [<span data-ttu-id="ddd3f-113">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ddd3f-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ddd3f-114">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ddd3f-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
