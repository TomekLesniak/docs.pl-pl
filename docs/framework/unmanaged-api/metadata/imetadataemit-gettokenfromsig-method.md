---
title: IMetaDataEmit::GetTokenFromSig — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type:
- apiref
ms.openlocfilehash: b41891227d94b66bf59128d620eba9da117fe92a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722053"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="84cd6-102">IMetaDataEmit::GetTokenFromSig — Metoda</span><span class="sxs-lookup"><span data-stu-id="84cd6-102">IMetaDataEmit::GetTokenFromSig Method</span></span>

<span data-ttu-id="84cd6-103">Pobiera token dla określonej sygnatury metadanych.</span><span class="sxs-lookup"><span data-stu-id="84cd6-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84cd6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="84cd6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (
    [in]  PCCOR_SIGNATURE pvSig,
    [in]  ULONG       cbSig,
    [out] mdSignature *pmsig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84cd6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="84cd6-105">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="84cd6-106">podczas Podpis, który ma zostać utrwalony i zapisany.</span><span class="sxs-lookup"><span data-stu-id="84cd6-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="84cd6-107">podczas Liczba bajtów w `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="84cd6-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="84cd6-108">określoną `mdSignature` Przypisany token.</span><span class="sxs-lookup"><span data-stu-id="84cd6-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84cd6-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="84cd6-109">Requirements</span></span>  

 <span data-ttu-id="84cd6-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84cd6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84cd6-111">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="84cd6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="84cd6-112">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="84cd6-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84cd6-113">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84cd6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84cd6-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="84cd6-114">See also</span></span>

- [<span data-ttu-id="84cd6-115">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="84cd6-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="84cd6-116">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="84cd6-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
