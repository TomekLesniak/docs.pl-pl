---
title: IMetaDataEmit::DefineSecurityAttributeSet — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
ms.openlocfilehash: 5caf07414c9e64169f272eb11169c4d4ee399c6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719466"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="7cf9b-102">IMetaDataEmit::DefineSecurityAttributeSet — Metoda</span><span class="sxs-lookup"><span data-stu-id="7cf9b-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>

<span data-ttu-id="7cf9b-103">Tworzy zestaw uprawnień zabezpieczeń do dołączenia do obiektu, do którego odwołuje się określony token.</span><span class="sxs-lookup"><span data-stu-id="7cf9b-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cf9b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7cf9b-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineSecurityAttributeSet (
    [in]  mdToken       tkObj,
    [in]  COR_SECATTR   rSecAttrs[],
    [in]  ULONG         cSecAttrs,
    [out] ULONG         *pulErrorAttr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cf9b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7cf9b-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="7cf9b-106">podczas Token, do którego są dołączone informacje o zabezpieczeniach.</span><span class="sxs-lookup"><span data-stu-id="7cf9b-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="7cf9b-107">podczas Tablica `COR_SECATTR` struktur.</span><span class="sxs-lookup"><span data-stu-id="7cf9b-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="7cf9b-108">podczas Liczba elementów w `rSecAttrs` .</span><span class="sxs-lookup"><span data-stu-id="7cf9b-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="7cf9b-109">określoną Jeśli metoda zakończy się niepowodzeniem, określa indeks `rSecAttrs` elementu, który spowodował problem.</span><span class="sxs-lookup"><span data-stu-id="7cf9b-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cf9b-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7cf9b-110">Requirements</span></span>  

 <span data-ttu-id="7cf9b-111">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cf9b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cf9b-112">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7cf9b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7cf9b-113">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7cf9b-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7cf9b-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cf9b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf9b-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7cf9b-115">See also</span></span>

- [<span data-ttu-id="7cf9b-116">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7cf9b-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7cf9b-117">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="7cf9b-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
