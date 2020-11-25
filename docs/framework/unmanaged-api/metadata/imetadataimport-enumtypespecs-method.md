---
title: IMetaDataImport::EnumTypeSpecs — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
ms.openlocfilehash: 38c9f8df12b0fc83a236d2cb7c32d1198be7096d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719817"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="257bf-102">IMetaDataImport::EnumTypeSpecs — Metoda</span><span class="sxs-lookup"><span data-stu-id="257bf-102">IMetaDataImport::EnumTypeSpecs Method</span></span>

<span data-ttu-id="257bf-103">Wylicza tokeny elementu TypeSpec zdefiniowane w bieżącym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="257bf-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="257bf-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="257bf-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="257bf-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="257bf-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="257bf-106">[in. out] Wskaźnik do modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="257bf-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="257bf-107">Ta wartość musi być RÓWNa NULL dla pierwszego wywołania tej metody.</span><span class="sxs-lookup"><span data-stu-id="257bf-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="257bf-108">określoną Tablica służąca do przechowywania tokenów elementu TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="257bf-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="257bf-109">podczas Maksymalny rozmiar `rTypeSpecs` tablicy.</span><span class="sxs-lookup"><span data-stu-id="257bf-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="257bf-110">określoną Liczba zwróconych tokenów elementu TypeSpec w `rTypeSpecs` .</span><span class="sxs-lookup"><span data-stu-id="257bf-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="257bf-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="257bf-111">Return Value</span></span>  
  
|<span data-ttu-id="257bf-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="257bf-112">HRESULT</span></span>|<span data-ttu-id="257bf-113">Opis</span><span class="sxs-lookup"><span data-stu-id="257bf-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="257bf-114">`EnumTypeSpecs` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="257bf-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="257bf-115">Brak tokenów do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="257bf-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="257bf-116">W takim przypadku `pcTypeSpecs` jest równa zero.</span><span class="sxs-lookup"><span data-stu-id="257bf-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="257bf-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="257bf-117">Remarks</span></span>  

 <span data-ttu-id="257bf-118">Tokeny elementu TypeSpec są tworzone przez metodę [IMetaDataEmit:: GetTokenFromTypeSpec —](imetadataemit-gettokenfromtypespec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="257bf-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="257bf-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="257bf-119">Requirements</span></span>  

 <span data-ttu-id="257bf-120">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="257bf-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="257bf-121">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="257bf-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="257bf-122">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="257bf-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="257bf-123">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="257bf-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="257bf-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="257bf-124">See also</span></span>

- [<span data-ttu-id="257bf-125">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="257bf-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="257bf-126">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="257bf-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
