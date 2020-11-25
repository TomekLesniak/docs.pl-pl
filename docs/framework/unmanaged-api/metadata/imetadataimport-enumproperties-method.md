---
title: IMetaDataImport::EnumProperties — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumProperties
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type:
- apiref
ms.openlocfilehash: 24ee37a36e34c74258e1c750ba424640c0496f0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728254"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="9e773-102">IMetaDataImport::EnumProperties — Metoda</span><span class="sxs-lookup"><span data-stu-id="9e773-102">IMetaDataImport::EnumProperties Method</span></span>

<span data-ttu-id="9e773-103">Wylicza tokeny PropertyDef reprezentujące właściwości typu, do którego odwołuje się określony token TypeDef.</span><span class="sxs-lookup"><span data-stu-id="9e773-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e773-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9e773-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e773-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="9e773-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="9e773-106">[in. out] Wskaźnik do modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="9e773-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="9e773-107">Musi ona mieć wartość NULL dla pierwszego wywołania tej metody.</span><span class="sxs-lookup"><span data-stu-id="9e773-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="9e773-108">podczas Token TypeDef reprezentujący typ z właściwościami do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="9e773-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="9e773-109">określoną Tablica służąca do przechowywania tokenów PropertyDef.</span><span class="sxs-lookup"><span data-stu-id="9e773-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9e773-110">podczas Maksymalny rozmiar `rProperties` tablicy.</span><span class="sxs-lookup"><span data-stu-id="9e773-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="9e773-111">określoną Liczba tokenów PropertyDef zwróconych w `rProperties` .</span><span class="sxs-lookup"><span data-stu-id="9e773-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e773-112">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="9e773-112">Return Value</span></span>  
  
|<span data-ttu-id="9e773-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e773-113">HRESULT</span></span>|<span data-ttu-id="9e773-114">Opis</span><span class="sxs-lookup"><span data-stu-id="9e773-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9e773-115">`EnumProperties` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="9e773-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9e773-116">Brak tokenów do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="9e773-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="9e773-117">W takim przypadku `pcProperties` jest równa zero.</span><span class="sxs-lookup"><span data-stu-id="9e773-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e773-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9e773-118">Requirements</span></span>  

 <span data-ttu-id="9e773-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e773-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e773-120">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9e773-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9e773-121">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9e773-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9e773-122">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e773-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e773-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9e773-123">See also</span></span>

- [<span data-ttu-id="9e773-124">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9e773-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="9e773-125">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9e773-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
