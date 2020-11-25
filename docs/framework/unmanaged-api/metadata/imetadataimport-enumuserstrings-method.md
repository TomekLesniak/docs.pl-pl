---
title: IMetaDataImport::EnumUserStrings — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUserStrings
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type:
- apiref
ms.openlocfilehash: c7dcc740dcf9b228713693a57dc8ef96d215ebad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716567"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="7fe76-102">IMetaDataImport::EnumUserStrings — Metoda</span><span class="sxs-lookup"><span data-stu-id="7fe76-102">IMetaDataImport::EnumUserStrings Method</span></span>

<span data-ttu-id="7fe76-103">Wylicza tokeny ciągów reprezentujące stałe ciągi w bieżącym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="7fe76-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fe76-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7fe76-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fe76-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7fe76-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="7fe76-106">[in. out] Wskaźnik do modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="7fe76-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7fe76-107">Musi ona mieć wartość NULL dla pierwszego wywołania tej metody.</span><span class="sxs-lookup"><span data-stu-id="7fe76-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="7fe76-108">określoną Tablica służąca do przechowywania tokenów ciągów.</span><span class="sxs-lookup"><span data-stu-id="7fe76-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7fe76-109">podczas Maksymalny rozmiar `rStrings` tablicy.</span><span class="sxs-lookup"><span data-stu-id="7fe76-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="7fe76-110">określoną Liczba tokenów ciągu zwróconych w `rStrings` .</span><span class="sxs-lookup"><span data-stu-id="7fe76-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7fe76-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="7fe76-111">Return Value</span></span>  
  
|<span data-ttu-id="7fe76-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7fe76-112">HRESULT</span></span>|<span data-ttu-id="7fe76-113">Opis</span><span class="sxs-lookup"><span data-stu-id="7fe76-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7fe76-114">`EnumUserStrings` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="7fe76-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7fe76-115">Brak tokenów do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="7fe76-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="7fe76-116">W takim przypadku `pcStrings` jest równa zero.</span><span class="sxs-lookup"><span data-stu-id="7fe76-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fe76-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7fe76-117">Remarks</span></span>  

 <span data-ttu-id="7fe76-118">Tokeny ciągów są tworzone przez metodę [IMetaDataEmit::D efineuserstring](imetadataemit-defineuserstring-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7fe76-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="7fe76-119">Ta metoda jest przeznaczona do użycia przez przeglądarkę metadanych, a nie przez kompilator.</span><span class="sxs-lookup"><span data-stu-id="7fe76-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fe76-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7fe76-120">Requirements</span></span>  

 <span data-ttu-id="7fe76-121">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fe76-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fe76-122">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7fe76-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7fe76-123">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7fe76-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7fe76-124">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fe76-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fe76-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7fe76-125">See also</span></span>

- [<span data-ttu-id="7fe76-126">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7fe76-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="7fe76-127">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7fe76-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
