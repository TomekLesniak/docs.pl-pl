---
title: IMetaDataImport::EnumCustomAttributes — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
ms.openlocfilehash: 3b12200dae23a7b6a2f6e1654e46fdf74dc90968
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700538"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="65704-102">IMetaDataImport::EnumCustomAttributes — Metoda</span><span class="sxs-lookup"><span data-stu-id="65704-102">IMetaDataImport::EnumCustomAttributes Method</span></span>

<span data-ttu-id="65704-103">Wylicza niestandardowe tokeny definicji atrybutów skojarzone z określonym typem lub członkiem.</span><span class="sxs-lookup"><span data-stu-id="65704-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65704-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="65704-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes (
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,
   [in]  mdToken            tkType,
   [out] mdCustomAttribute  rCustomAttributes[],
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65704-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="65704-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="65704-106">[in. out] Wskaźnik do zwróconego modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="65704-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="65704-107">podczas Token dla zakresu wyliczenia lub zero dla wszystkich atrybutów niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="65704-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="65704-108">podczas Token dla konstruktora typu atrybutów do wyliczenia lub `null` dla wszystkich typów.</span><span class="sxs-lookup"><span data-stu-id="65704-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="65704-109">określoną Tablica tokenów atrybutów niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="65704-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="65704-110">podczas Maksymalny rozmiar `rCustomAttributes` tablicy.</span><span class="sxs-lookup"><span data-stu-id="65704-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="65704-111">[out, opcjonalne] Rzeczywista liczba zwracanych wartości tokenu `rCustomAttributes` .</span><span class="sxs-lookup"><span data-stu-id="65704-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65704-112">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="65704-112">Return Value</span></span>  
  
|<span data-ttu-id="65704-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65704-113">HRESULT</span></span>|<span data-ttu-id="65704-114">Opis</span><span class="sxs-lookup"><span data-stu-id="65704-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="65704-115">`EnumCustomAttributes` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="65704-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="65704-116">Brak atrybutów niestandardowych do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="65704-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="65704-117">W takim przypadku `pcCustomAttributes` jest równa zero.</span><span class="sxs-lookup"><span data-stu-id="65704-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65704-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="65704-118">Requirements</span></span>  

 <span data-ttu-id="65704-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65704-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65704-120">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="65704-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="65704-121">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="65704-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="65704-122">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65704-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65704-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="65704-123">See also</span></span>

- [<span data-ttu-id="65704-124">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="65704-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="65704-125">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="65704-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
