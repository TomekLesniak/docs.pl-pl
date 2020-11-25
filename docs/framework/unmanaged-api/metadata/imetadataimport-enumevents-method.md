---
title: IMetaDataImport::EnumEvents — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumEvents
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type:
- apiref
ms.openlocfilehash: 3a181f1ef29810058c57bdb13338a01aa1fe7dff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700473"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="b3cca-102">IMetaDataImport::EnumEvents — Metoda</span><span class="sxs-lookup"><span data-stu-id="b3cca-102">IMetaDataImport::EnumEvents Method</span></span>

<span data-ttu-id="b3cca-103">Wylicza tokeny definicji zdarzeń dla określonego tokenu TypeDef.</span><span class="sxs-lookup"><span data-stu-id="b3cca-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3cca-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b3cca-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdEvent     rEvents[],
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3cca-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b3cca-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="b3cca-106">[in. out] Wskaźnik do modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="b3cca-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="b3cca-107">podczas Token TypeDef, którego definicje zdarzeń mają zostać wyliczone.</span><span class="sxs-lookup"><span data-stu-id="b3cca-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="b3cca-108">określoną Tablica zwracanych zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="b3cca-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b3cca-109">podczas Maksymalny rozmiar `rEvents` tablicy.</span><span class="sxs-lookup"><span data-stu-id="b3cca-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="b3cca-110">określoną Rzeczywista liczba zdarzeń zwrócona w `rEvents` .</span><span class="sxs-lookup"><span data-stu-id="b3cca-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3cca-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="b3cca-111">Return Value</span></span>  
  
|<span data-ttu-id="b3cca-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b3cca-112">HRESULT</span></span>|<span data-ttu-id="b3cca-113">Opis</span><span class="sxs-lookup"><span data-stu-id="b3cca-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b3cca-114">`EnumEvents` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="b3cca-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b3cca-115">Brak zdarzeń do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="b3cca-115">There are no events to enumerate.</span></span> <span data-ttu-id="b3cca-116">W takim przypadku `pcEvents` jest równa zero.</span><span class="sxs-lookup"><span data-stu-id="b3cca-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3cca-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b3cca-117">Requirements</span></span>  

 <span data-ttu-id="b3cca-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3cca-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3cca-119">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b3cca-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3cca-120">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3cca-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3cca-121">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3cca-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3cca-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b3cca-122">See also</span></span>

- [<span data-ttu-id="b3cca-123">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b3cca-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="b3cca-124">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b3cca-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
