---
title: IMetaDataImport::ResetEnum — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
ms.openlocfilehash: 52c35b3bd726d4c83c6745bf99940faa44ea7338
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702853"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="44031-102">IMetaDataImport::ResetEnum — Metoda</span><span class="sxs-lookup"><span data-stu-id="44031-102">IMetaDataImport::ResetEnum Method</span></span>

<span data-ttu-id="44031-103">Resetuje określony moduł wyliczający do określonego położenia.</span><span class="sxs-lookup"><span data-stu-id="44031-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44031-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="44031-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44031-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="44031-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="44031-106">podczas Moduł wyliczający do zresetowania.</span><span class="sxs-lookup"><span data-stu-id="44031-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="44031-107">podczas Nowa pozycja, w której ma zostać umieszczony moduł wyliczający.</span><span class="sxs-lookup"><span data-stu-id="44031-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44031-108">Wymagania</span><span class="sxs-lookup"><span data-stu-id="44031-108">Requirements</span></span>  

 <span data-ttu-id="44031-109">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44031-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44031-110">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="44031-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44031-111">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="44031-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="44031-112">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44031-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44031-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="44031-113">See also</span></span>

- [<span data-ttu-id="44031-114">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="44031-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="44031-115">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="44031-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
