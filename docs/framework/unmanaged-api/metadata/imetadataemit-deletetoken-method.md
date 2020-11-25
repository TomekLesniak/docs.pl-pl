---
title: IMetaDataEmit::DeleteToken — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type:
- apiref
ms.openlocfilehash: eaa465855c9e933286bcdd189e62048510088ec7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722079"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="37166-102">IMetaDataEmit::DeleteToken — Metoda</span><span class="sxs-lookup"><span data-stu-id="37166-102">IMetaDataEmit::DeleteToken Method</span></span>

<span data-ttu-id="37166-103">Usuwa określony token z bieżącego zakresu metadanych.</span><span class="sxs-lookup"><span data-stu-id="37166-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37166-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="37166-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteToken (
    [in]  mdToken     tkObj
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37166-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="37166-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="37166-106">podczas Token, który ma zostać usunięty.</span><span class="sxs-lookup"><span data-stu-id="37166-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37166-107">Wymagania</span><span class="sxs-lookup"><span data-stu-id="37166-107">Requirements</span></span>  

 <span data-ttu-id="37166-108">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37166-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37166-109">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="37166-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37166-110">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="37166-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37166-111">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37166-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37166-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="37166-112">See also</span></span>

- [<span data-ttu-id="37166-113">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="37166-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="37166-114">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="37166-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
