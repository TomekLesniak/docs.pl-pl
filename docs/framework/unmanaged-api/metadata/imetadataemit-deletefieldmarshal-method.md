---
title: IMetaDataEmit::DeleteFieldMarshal — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteFieldMarshal
helpviewer_keywords:
- IMetaDataEmit::DeleteFieldMarshal method [.NET Framework metadata]
- DeleteFieldMarshal method [.NET Framework metadata]
ms.assetid: 7c75aef9-c742-4b33-a14b-56ff94b0f725
topic_type:
- apiref
ms.openlocfilehash: 5989c45782b4f83ecfa285cb305080320abf6a3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700551"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="519ac-102">IMetaDataEmit::DeleteFieldMarshal — Metoda</span><span class="sxs-lookup"><span data-stu-id="519ac-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>

<span data-ttu-id="519ac-103">Niszczy sygnaturę metadanych kierowania PInvoke dla obiektu, do którego odwołuje się określony token.</span><span class="sxs-lookup"><span data-stu-id="519ac-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="519ac-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="519ac-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="519ac-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="519ac-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="519ac-106">podczas `mdFieldDef` Token lub `mdParamDef` , który reprezentuje pole lub parametr, dla którego ma zostać usunięta sygnatura organizowania metadanych.</span><span class="sxs-lookup"><span data-stu-id="519ac-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="519ac-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="519ac-107">Requirements</span></span>  

 <span data-ttu-id="519ac-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="519ac-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="519ac-109">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="519ac-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="519ac-110">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="519ac-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="519ac-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="519ac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="519ac-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="519ac-112">See also</span></span>

- [<span data-ttu-id="519ac-113">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="519ac-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="519ac-114">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="519ac-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
