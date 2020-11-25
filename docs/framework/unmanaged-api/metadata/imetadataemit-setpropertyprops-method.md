---
title: IMetaDataEmit::SetPropertyProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
ms.openlocfilehash: 553a82475f241fac3a56c1fb009e3ed56b2c14f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704256"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="2323e-102">IMetaDataEmit::SetPropertyProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="2323e-102">IMetaDataEmit::SetPropertyProps Method</span></span>

<span data-ttu-id="2323e-103">Ustawia funkcje przechowywane w metadanych dla właściwości zdefiniowanej przez poprzednie wywołanie [metody DefineProperty —](imetadataemit-defineproperty-method.md).</span><span class="sxs-lookup"><span data-stu-id="2323e-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2323e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="2323e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertyProps (
    [in]  mdProperty      pr,
    [in]  DWORD           dwPropFlags,
    [in]  DWORD           dwCPlusTypeFlag,
    [in]  void const      *pValue,
    [in]  ULONG           cchValue,
    [in]  mdMethodDef     mdSetter,
    [in]  mdMethodDef     mdGetter,
    [in]  mdMethodDef     rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2323e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="2323e-105">Parameters</span></span>  

 `pr`  
 <span data-ttu-id="2323e-106">podczas Token dla właściwości, która ma zostać zmieniona.</span><span class="sxs-lookup"><span data-stu-id="2323e-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="2323e-107">podczas Flagi właściwości.</span><span class="sxs-lookup"><span data-stu-id="2323e-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="2323e-108">podczas Typ wartości domyślnej właściwości.</span><span class="sxs-lookup"><span data-stu-id="2323e-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="2323e-109">podczas Wartość domyślna właściwości.</span><span class="sxs-lookup"><span data-stu-id="2323e-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="2323e-110">podczas Liczba znaków (Unicode) w `pValue` .</span><span class="sxs-lookup"><span data-stu-id="2323e-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="2323e-111">podczas Metoda, która ustawia wartość właściwości.</span><span class="sxs-lookup"><span data-stu-id="2323e-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="2323e-112">podczas Metoda, która pobiera wartość właściwości.</span><span class="sxs-lookup"><span data-stu-id="2323e-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="2323e-113">podczas Tablica innych metod skojarzonych z właściwością.</span><span class="sxs-lookup"><span data-stu-id="2323e-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="2323e-114">Przerwij tę tablicę przy użyciu `mdTokenNil` tokenu.</span><span class="sxs-lookup"><span data-stu-id="2323e-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2323e-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="2323e-115">Requirements</span></span>  

 <span data-ttu-id="2323e-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2323e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2323e-117">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2323e-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2323e-118">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2323e-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2323e-119">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2323e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2323e-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2323e-120">See also</span></span>

- [<span data-ttu-id="2323e-121">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2323e-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2323e-122">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="2323e-122">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
