---
title: IMetaDataEmit::SetCustomAttributeValue — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
ms.openlocfilehash: c4ea325a755ed05eed378d9201068de31ca8114f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681587"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="35710-102">IMetaDataEmit::SetCustomAttributeValue — Metoda</span><span class="sxs-lookup"><span data-stu-id="35710-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>

<span data-ttu-id="35710-103">Ustawia lub aktualizuje wartość atrybutu niestandardowego zdefiniowanego przez poprzednie wywołanie do [IMetaDataEmit::D efinecustomattribute](imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="35710-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35710-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="35710-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCustomAttributeValue (
    [in]  mdCustomAttribute       pcv,
    [in]  void const              *pCustomAttribute,
    [in]  ULONG                   cbCustomAttribute
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35710-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="35710-105">Parameters</span></span>  

 `pcv`  
 <span data-ttu-id="35710-106">podczas Token docelowego atrybutu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="35710-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="35710-107">podczas Wskaźnik do tablicy zawierającej atrybut niestandardowy.</span><span class="sxs-lookup"><span data-stu-id="35710-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="35710-108">podczas Rozmiar atrybutu niestandardowego w bajtach.</span><span class="sxs-lookup"><span data-stu-id="35710-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35710-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="35710-109">Requirements</span></span>  

 <span data-ttu-id="35710-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35710-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35710-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="35710-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35710-112">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35710-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35710-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35710-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35710-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="35710-114">See also</span></span>

- [<span data-ttu-id="35710-115">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="35710-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="35710-116">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="35710-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
