---
title: IMetaDataEmit::DefineTypeDef — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: 2e75b6322e40fe010e9e0a3412a99c0d3460afae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719362"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="39d2f-102">IMetaDataEmit::DefineTypeDef — Metoda</span><span class="sxs-lookup"><span data-stu-id="39d2f-102">IMetaDataEmit::DefineTypeDef Method</span></span>

<span data-ttu-id="39d2f-103">Tworzy definicję typu dla typu środowiska uruchomieniowego języka wspólnego i pobiera token metadanych dla tej definicji typu.</span><span class="sxs-lookup"><span data-stu-id="39d2f-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39d2f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="39d2f-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39d2f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="39d2f-105">Parameters</span></span>  

 `szTypeDef`  
 <span data-ttu-id="39d2f-106">podczas Nazwa typu w formacie Unicode.</span><span class="sxs-lookup"><span data-stu-id="39d2f-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="39d2f-107">[w] `TypeDef` Attributes.</span><span class="sxs-lookup"><span data-stu-id="39d2f-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="39d2f-108">To jest maska bitów `CoreTypeAttr` wartości.</span><span class="sxs-lookup"><span data-stu-id="39d2f-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="39d2f-109">podczas Token klasy bazowej.</span><span class="sxs-lookup"><span data-stu-id="39d2f-109">[in] The token of the base class.</span></span> <span data-ttu-id="39d2f-110">Musi być albo `mdTypeDef` `mdTypeRef` tokenem.</span><span class="sxs-lookup"><span data-stu-id="39d2f-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="39d2f-111">podczas Tablica tokenów określająca interfejsy, które implementuje Ta klasa lub interfejs.</span><span class="sxs-lookup"><span data-stu-id="39d2f-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="39d2f-112">określoną `mdTypeDef` Przypisany token.</span><span class="sxs-lookup"><span data-stu-id="39d2f-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39d2f-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="39d2f-113">Remarks</span></span>  

 <span data-ttu-id="39d2f-114">Flaga w `dwTypeDefFlags` określa, czy tworzony typ jest typem referencyjnym systemu typu wspólnego (Class lub Interface) czy typem wartości typu wspólnego systemu.</span><span class="sxs-lookup"><span data-stu-id="39d2f-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="39d2f-115">W zależności od dostarczonych parametrów, ta metoda jako efekt uboczny może również utworzyć `mdInterfaceImpl` rekord dla każdego interfejsu, który jest dziedziczony lub zaimplementowany przez ten typ.</span><span class="sxs-lookup"><span data-stu-id="39d2f-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="39d2f-116">Jednakże ta metoda nie zwraca żadnego z tych `mdInterfaceImpl` tokenów.</span><span class="sxs-lookup"><span data-stu-id="39d2f-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="39d2f-117">Jeśli klient chce później dodać lub zmodyfikować `mdInterfaceImpl` token, musi użyć `IMetaDataImport` interfejsu, aby je wyliczyć.</span><span class="sxs-lookup"><span data-stu-id="39d2f-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="39d2f-118">Jeśli chcesz używać semantyki COM `[default]` interfejsu, należy podać domyślny interfejs jako pierwszy element w `rtkImplements` ; zestaw atrybutów niestandardowych w klasie wskazuje, że Klasa ma interfejs domyślny (który jest zawsze traktowany jako pierwszy `mdInterfaceImpl` token zadeklarowany dla klasy).</span><span class="sxs-lookup"><span data-stu-id="39d2f-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="39d2f-119">Każdy element `rtkImplements` tablicy zawiera `mdTypeDef` `mdTypeRef` token lub.</span><span class="sxs-lookup"><span data-stu-id="39d2f-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="39d2f-120">Ostatni element w tablicy musi być `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="39d2f-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39d2f-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="39d2f-121">Requirements</span></span>  

 <span data-ttu-id="39d2f-122">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39d2f-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39d2f-123">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="39d2f-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39d2f-124">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="39d2f-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39d2f-125">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39d2f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d2f-126">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="39d2f-126">See also</span></span>

- [<span data-ttu-id="39d2f-127">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="39d2f-127">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="39d2f-128">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="39d2f-128">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
