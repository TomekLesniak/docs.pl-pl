---
title: IMetaDataImport::EnumFields — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFields
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFields
helpviewer_keywords:
- EnumFields method [.NET Framework metadata]
- IMetaDataImport::EnumFields method [.NET Framework metadata]
ms.assetid: 1d23247e-c58c-45db-afd8-83aa89cde18e
topic_type:
- apiref
ms.openlocfilehash: 74035e9551cb1d622b326e511c3884e1eadf057f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711601"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="e518d-102">IMetaDataImport::EnumFields — Metoda</span><span class="sxs-lookup"><span data-stu-id="e518d-102">IMetaDataImport::EnumFields Method</span></span>

<span data-ttu-id="e518d-103">Wylicza tokeny FieldDef dla typu, do którego odwołuje się określony token TypeDef.</span><span class="sxs-lookup"><span data-stu-id="e518d-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e518d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e518d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e518d-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="e518d-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="e518d-106">[in. out] Wskaźnik do modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="e518d-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="e518d-107">podczas Token TypeDef klasy, której pola mają zostać wyliczone.</span><span class="sxs-lookup"><span data-stu-id="e518d-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="e518d-108">określoną Lista tokenów FieldDef.</span><span class="sxs-lookup"><span data-stu-id="e518d-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e518d-109">podczas Maksymalny rozmiar `rFields` tablicy.</span><span class="sxs-lookup"><span data-stu-id="e518d-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e518d-110">określoną Rzeczywista liczba tokenów FieldDef zwrócona w `rFields` .</span><span class="sxs-lookup"><span data-stu-id="e518d-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e518d-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="e518d-111">Return Value</span></span>  
  
|<span data-ttu-id="e518d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e518d-112">HRESULT</span></span>|<span data-ttu-id="e518d-113">Opis</span><span class="sxs-lookup"><span data-stu-id="e518d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e518d-114">`EnumFields` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="e518d-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e518d-115">Brak pól do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="e518d-115">There are no fields to enumerate.</span></span> <span data-ttu-id="e518d-116">W takim przypadku `pcTokens` jest równa zero.</span><span class="sxs-lookup"><span data-stu-id="e518d-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e518d-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e518d-117">Requirements</span></span>  

 <span data-ttu-id="e518d-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e518d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e518d-119">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e518d-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e518d-120">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e518d-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e518d-121">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e518d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e518d-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e518d-122">See also</span></span>

- [<span data-ttu-id="e518d-123">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e518d-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e518d-124">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="e518d-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
