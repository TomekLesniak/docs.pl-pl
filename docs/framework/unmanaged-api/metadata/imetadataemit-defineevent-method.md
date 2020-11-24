---
title: IMetaDataEmit::DefineEvent — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: 3c03497f48b8199da545d796637e5f8a5c532362
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675701"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="85b8e-102">IMetaDataEmit::DefineEvent — Metoda</span><span class="sxs-lookup"><span data-stu-id="85b8e-102">IMetaDataEmit::DefineEvent Method</span></span>

<span data-ttu-id="85b8e-103">Tworzy definicję zdarzenia z określonym podpisem metadanych i pobiera token do tej definicji zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="85b8e-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85b8e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="85b8e-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineEvent (
    [in]  mdTypeDef    td,
    [in]  LPCWSTR      szEvent,
    [in]  DWORD        dwEventFlags,
    [in]  mdToken      tkEventType,
    [in]  mdMethodDef  mdAddOn,
    [in]  mdMethodDef  mdRemoveOn,
    [in]  mdMethodDef  mdFire,
    [in]  mdMethodDef  rmdOtherMethods[],
    [out] mdEvent      *pmdEvent
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85b8e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="85b8e-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="85b8e-106">podczas Token dla docelowej klasy lub interfejsu.</span><span class="sxs-lookup"><span data-stu-id="85b8e-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="85b8e-107">Jest to `mdTypeDef` `mdTypeDefNil` token lub.</span><span class="sxs-lookup"><span data-stu-id="85b8e-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="85b8e-108">podczas Nazwa zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="85b8e-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="85b8e-109">podczas Flagi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="85b8e-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="85b8e-110">podczas Token dla klasy Event.</span><span class="sxs-lookup"><span data-stu-id="85b8e-110">[in] The token for the event class.</span></span> <span data-ttu-id="85b8e-111">Jest to `mdTypeDef` , a `mdTypeRef` , lub `mdTokenNil` token.</span><span class="sxs-lookup"><span data-stu-id="85b8e-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="85b8e-112">podczas Metoda używana do subskrybowania zdarzenia lub wartość null.</span><span class="sxs-lookup"><span data-stu-id="85b8e-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="85b8e-113">podczas Metoda używana do anulowania subskrypcji zdarzenia lub wartość null.</span><span class="sxs-lookup"><span data-stu-id="85b8e-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="85b8e-114">podczas Metoda używana (przez klasę pochodną) do podniesienia zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="85b8e-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="85b8e-115">podczas Tablica tokenów dla innych metod skojarzonych ze zdarzeniem.</span><span class="sxs-lookup"><span data-stu-id="85b8e-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="85b8e-116">Tablica została zakończona z `mdMethodDefNil` tokenem.</span><span class="sxs-lookup"><span data-stu-id="85b8e-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="85b8e-117">określoną Token metadanych przypisany do zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="85b8e-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85b8e-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="85b8e-118">Requirements</span></span>  

 <span data-ttu-id="85b8e-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85b8e-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85b8e-120">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="85b8e-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85b8e-121">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85b8e-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85b8e-122">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85b8e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85b8e-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="85b8e-123">See also</span></span>

- [<span data-ttu-id="85b8e-124">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="85b8e-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="85b8e-125">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="85b8e-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
