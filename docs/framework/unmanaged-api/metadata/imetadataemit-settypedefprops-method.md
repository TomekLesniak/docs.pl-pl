---
title: IMetaDataEmit::SetTypeDefProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: 2f572f66f16ff701350fde3b05be822b9e8c78b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706835"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="91a39-102">IMetaDataEmit::SetTypeDefProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="91a39-102">IMetaDataEmit::SetTypeDefProps Method</span></span>

<span data-ttu-id="91a39-103">Ustawia funkcje typu zdefiniowanego przez poprzednie wywołanie [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="91a39-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a39-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="91a39-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91a39-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="91a39-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="91a39-106">podczas `mdTypeDef` Token uzyskany od oryginalnego wywołania do [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="91a39-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="91a39-107">[w] `TypeDef` Attributes.</span><span class="sxs-lookup"><span data-stu-id="91a39-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="91a39-108">To jest maska bitów `CorTypeAttr` wartości.</span><span class="sxs-lookup"><span data-stu-id="91a39-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="91a39-109">podczas `mdToken` Klasy podstawowej.</span><span class="sxs-lookup"><span data-stu-id="91a39-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="91a39-110">Uzyskano od poprzedniego wywołania do [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md)lub `null` .</span><span class="sxs-lookup"><span data-stu-id="91a39-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="91a39-111">podczas Tablica tokenów dla interfejsów, które implementuje ten typ.</span><span class="sxs-lookup"><span data-stu-id="91a39-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="91a39-112">Te `mdTypeRef` tokeny są uzyskiwane przy użyciu [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="91a39-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="91a39-113">Ostatni element tablicy musi być `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="91a39-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91a39-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="91a39-114">Requirements</span></span>  

 <span data-ttu-id="91a39-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91a39-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91a39-116">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="91a39-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="91a39-117">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="91a39-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91a39-118">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91a39-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a39-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="91a39-119">See also</span></span>

- [<span data-ttu-id="91a39-120">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="91a39-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="91a39-121">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="91a39-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
