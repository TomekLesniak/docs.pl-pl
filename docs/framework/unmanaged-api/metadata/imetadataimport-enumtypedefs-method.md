---
title: IMetaDataImport::EnumTypeDefs — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: 4545f5f8d78e588c655a72340210a785b0feb619
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720415"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="1c7f6-102">IMetaDataImport::EnumTypeDefs — Metoda</span><span class="sxs-lookup"><span data-stu-id="1c7f6-102">IMetaDataImport::EnumTypeDefs Method</span></span>

<span data-ttu-id="1c7f6-103">Wylicza tokeny TypeDef reprezentujące wszystkie typy w bieżącym zakresie.</span><span class="sxs-lookup"><span data-stu-id="1c7f6-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c7f6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1c7f6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c7f6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="1c7f6-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="1c7f6-106">określoną Wskaźnik do nowego modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="1c7f6-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="1c7f6-107">Musi ona mieć wartość NULL dla pierwszego wywołania tej metody.</span><span class="sxs-lookup"><span data-stu-id="1c7f6-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="1c7f6-108">podczas Tablica służąca do przechowywania tokenów TypeDef.</span><span class="sxs-lookup"><span data-stu-id="1c7f6-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1c7f6-109">podczas Maksymalny rozmiar `rTypeDefs` tablicy.</span><span class="sxs-lookup"><span data-stu-id="1c7f6-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="1c7f6-110">określoną Liczba tokenów TypeDef zwróconych w `rTypeDefs` .</span><span class="sxs-lookup"><span data-stu-id="1c7f6-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c7f6-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="1c7f6-111">Return Value</span></span>  
  
|<span data-ttu-id="1c7f6-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1c7f6-112">HRESULT</span></span>|<span data-ttu-id="1c7f6-113">Opis</span><span class="sxs-lookup"><span data-stu-id="1c7f6-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1c7f6-114">`EnumTypeDefs` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="1c7f6-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1c7f6-115">Brak tokenów do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="1c7f6-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="1c7f6-116">W takim przypadku `pcTypeDefs` jest równa zero.</span><span class="sxs-lookup"><span data-stu-id="1c7f6-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c7f6-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1c7f6-117">Remarks</span></span>  

 <span data-ttu-id="1c7f6-118">Token TypeDef reprezentuje typ, taki jak Klasa lub interfejs, a także dowolny typ dodany za pomocą mechanizmu rozszerzalności.</span><span class="sxs-lookup"><span data-stu-id="1c7f6-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c7f6-119">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1c7f6-119">Requirements</span></span>  

 <span data-ttu-id="1c7f6-120">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c7f6-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c7f6-121">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1c7f6-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1c7f6-122">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1c7f6-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c7f6-123">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c7f6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c7f6-124">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1c7f6-124">See also</span></span>

- [<span data-ttu-id="1c7f6-125">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="1c7f6-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1c7f6-126">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="1c7f6-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
