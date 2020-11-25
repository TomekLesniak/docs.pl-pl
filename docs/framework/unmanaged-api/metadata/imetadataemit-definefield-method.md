---
title: IMetaDataEmit::DefineField — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 2bc2b983171dc41d5ac37eda0359f1aaee4ebd6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725758"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="b9c1b-102">IMetaDataEmit::DefineField — Metoda</span><span class="sxs-lookup"><span data-stu-id="b9c1b-102">IMetaDataEmit::DefineField Method</span></span>

<span data-ttu-id="b9c1b-103">Tworzy definicję dla pola z określonym podpisem metadanych i pobiera token do tej definicji pola.</span><span class="sxs-lookup"><span data-stu-id="b9c1b-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9c1b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b9c1b-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineField (
    [in]  mdTypeDef   td,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwFieldFlags,
    [in]  PCCOR_SIGNATURE pvSigBlob,
    [in]  ULONG       cbSigBlob,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue,
    [out] mdFieldDef  *pmd
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9c1b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b9c1b-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="b9c1b-106">podczas `mdTypeDef` Token dla otaczającej klasy lub interfejsu.</span><span class="sxs-lookup"><span data-stu-id="b9c1b-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="b9c1b-107">podczas Nazwa pola w formacie Unicode.</span><span class="sxs-lookup"><span data-stu-id="b9c1b-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="b9c1b-108">podczas Atrybuty pola.</span><span class="sxs-lookup"><span data-stu-id="b9c1b-108">[in] The field attributes.</span></span> <span data-ttu-id="b9c1b-109">To jest maska bitów `CorFieldAttr` wartości.</span><span class="sxs-lookup"><span data-stu-id="b9c1b-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="b9c1b-110">podczas Podpis pola jako obiekt BLOB.</span><span class="sxs-lookup"><span data-stu-id="b9c1b-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="b9c1b-111">podczas Liczba bajtów w `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="b9c1b-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="b9c1b-112">podczas `ELEMENT_TYPE_` *\** Wartość stałej.</span><span class="sxs-lookup"><span data-stu-id="b9c1b-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="b9c1b-113">To jest `CorElementType` wartość.</span><span class="sxs-lookup"><span data-stu-id="b9c1b-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="b9c1b-114">Jeśli nie definiuje wartości stałej dla pola, użyj `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="b9c1b-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="b9c1b-115">podczas Stała wartość pola.</span><span class="sxs-lookup"><span data-stu-id="b9c1b-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="b9c1b-116">podczas Znaki w formacie (Unicode) `pValue` .</span><span class="sxs-lookup"><span data-stu-id="b9c1b-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="b9c1b-117">określoną `mdFieldDef` Przypisany token.</span><span class="sxs-lookup"><span data-stu-id="b9c1b-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9c1b-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b9c1b-118">Requirements</span></span>  

 <span data-ttu-id="b9c1b-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9c1b-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9c1b-120">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b9c1b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9c1b-121">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9c1b-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9c1b-122">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9c1b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9c1b-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b9c1b-123">See also</span></span>

- [<span data-ttu-id="b9c1b-124">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b9c1b-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b9c1b-125">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b9c1b-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
