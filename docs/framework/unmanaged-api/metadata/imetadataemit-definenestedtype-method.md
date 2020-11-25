---
title: IMetaDataEmit::DefineNestedType — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
ms.openlocfilehash: 99dc141cca0f911c8dd65645f6c22d950cc678d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719544"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="074ec-102">IMetaDataEmit::DefineNestedType — Metoda</span><span class="sxs-lookup"><span data-stu-id="074ec-102">IMetaDataEmit::DefineNestedType Method</span></span>

<span data-ttu-id="074ec-103">Tworzy sygnaturę metadanych definicji typu, zwraca `mdTypeDef` token dla tego typu i określa, że zdefiniowany typ jest składową typu, do którego odwołuje się `tdEncloser` parametr.</span><span class="sxs-lookup"><span data-stu-id="074ec-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="074ec-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="074ec-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="074ec-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="074ec-105">Parameters</span></span>  

 `szTypeDef`  
 <span data-ttu-id="074ec-106">podczas Nazwa typu w formacie Unicode.</span><span class="sxs-lookup"><span data-stu-id="074ec-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="074ec-107">[w] `TypeDef` Attributes.</span><span class="sxs-lookup"><span data-stu-id="074ec-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="074ec-108">To jest maska bitów `CorTypeAttr` wartości.</span><span class="sxs-lookup"><span data-stu-id="074ec-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="074ec-109">podczas Token klasy bazowej.</span><span class="sxs-lookup"><span data-stu-id="074ec-109">[in] The token of the base class.</span></span> <span data-ttu-id="074ec-110">Jest to albo `mdTypeDef` `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="074ec-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="074ec-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="074ec-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="074ec-112">podczas Tablica tokenów, które określają interfejsy, które implementuje Ta klasa lub interfejs.</span><span class="sxs-lookup"><span data-stu-id="074ec-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="074ec-113">podczas Token typu otaczającego.</span><span class="sxs-lookup"><span data-stu-id="074ec-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="074ec-114">Ostatni element tablicy musi być `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="074ec-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="074ec-115">określoną `mdTypeDef` Przypisany token.</span><span class="sxs-lookup"><span data-stu-id="074ec-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="074ec-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="074ec-116">Requirements</span></span>  

 <span data-ttu-id="074ec-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="074ec-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="074ec-118">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="074ec-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="074ec-119">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="074ec-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="074ec-120">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="074ec-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="074ec-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="074ec-121">See also</span></span>

- [<span data-ttu-id="074ec-122">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="074ec-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="074ec-123">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="074ec-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
