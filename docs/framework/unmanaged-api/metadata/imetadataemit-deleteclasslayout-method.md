---
title: IMetaDataEmit::DeleteClassLayout — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type:
- apiref
ms.openlocfilehash: d355e0e3b2461932384ca11d83d46fd1dc63b80e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732687"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="a4c87-102">IMetaDataEmit::DeleteClassLayout — Metoda</span><span class="sxs-lookup"><span data-stu-id="a4c87-102">IMetaDataEmit::DeleteClassLayout Method</span></span>

<span data-ttu-id="a4c87-103">Niszczy sygnaturę metadanych układu klasy dla typu reprezentowanego przez określony token.</span><span class="sxs-lookup"><span data-stu-id="a4c87-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4c87-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a4c87-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4c87-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a4c87-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="a4c87-106">podczas `mdTypeDef` Token metadanych reprezentujący typ, dla którego zostanie usunięty układ klasy.</span><span class="sxs-lookup"><span data-stu-id="a4c87-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4c87-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a4c87-107">Requirements</span></span>  

 <span data-ttu-id="a4c87-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4c87-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4c87-109">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a4c87-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4c87-110">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a4c87-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4c87-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4c87-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4c87-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a4c87-112">See also</span></span>

- [<span data-ttu-id="a4c87-113">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a4c87-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a4c87-114">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a4c87-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
