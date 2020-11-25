---
title: IMetaDataEmit::GetTokenFromTypeSpec — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
ms.openlocfilehash: 3a8f369728b8464850259518981bf6690cb17a01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722040"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="80556-102">IMetaDataEmit::GetTokenFromTypeSpec — Metoda</span><span class="sxs-lookup"><span data-stu-id="80556-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>

<span data-ttu-id="80556-103">Pobiera token metadanych dla typu z określonym podpisem metadanych.</span><span class="sxs-lookup"><span data-stu-id="80556-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80556-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="80556-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80556-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="80556-105">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="80556-106">podczas Zdefiniowany podpis.</span><span class="sxs-lookup"><span data-stu-id="80556-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="80556-107">podczas Liczba bajtów w `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="80556-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="80556-108">określoną `mdTypeSpec` Przypisany token.</span><span class="sxs-lookup"><span data-stu-id="80556-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80556-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="80556-109">Requirements</span></span>  

 <span data-ttu-id="80556-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80556-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80556-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="80556-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80556-112">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80556-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80556-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80556-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80556-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="80556-114">See also</span></span>

- [<span data-ttu-id="80556-115">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="80556-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="80556-116">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="80556-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
