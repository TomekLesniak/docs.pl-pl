---
title: IMetaDataEmit::DefineParam — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
ms.openlocfilehash: 5b3f89bb14be0d7128682f8702548545b1e50928
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719531"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="4e393-102">IMetaDataEmit::DefineParam — Metoda</span><span class="sxs-lookup"><span data-stu-id="4e393-102">IMetaDataEmit::DefineParam Method</span></span>

<span data-ttu-id="4e393-103">Tworzy definicję parametru z określonym podpisem dla metody przywoływanej przez określony token i pobiera token dla tej definicji parametru.</span><span class="sxs-lookup"><span data-stu-id="4e393-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e393-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4e393-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineParam (  
    [in]  mdMethodDef md,
    [in]  ULONG       ulParamSeq,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,
    [out] mdParamDef  *ppd
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e393-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="4e393-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="4e393-106">podczas Token dla metody, której parametr jest definiowany.</span><span class="sxs-lookup"><span data-stu-id="4e393-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="4e393-107">podczas Numer sekwencyjny parametru.</span><span class="sxs-lookup"><span data-stu-id="4e393-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="4e393-108">podczas Nazwa parametru w formacie Unicode.</span><span class="sxs-lookup"><span data-stu-id="4e393-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="4e393-109">podczas Flagi dla parametru.</span><span class="sxs-lookup"><span data-stu-id="4e393-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="4e393-110">To jest maska bitów `CorParamAttr` wartości.</span><span class="sxs-lookup"><span data-stu-id="4e393-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="4e393-111">[w] `ELEMENT_TYPE_` *\** dla wartości stałej.</span><span class="sxs-lookup"><span data-stu-id="4e393-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="4e393-112">podczas Stała wartość parametru.</span><span class="sxs-lookup"><span data-stu-id="4e393-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="4e393-113">podczas Rozmiar, w znakach Unicode, z `pValue` .</span><span class="sxs-lookup"><span data-stu-id="4e393-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="4e393-114">określoną `mdParamDef` Przypisany token.</span><span class="sxs-lookup"><span data-stu-id="4e393-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e393-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4e393-115">Remarks</span></span>  

 <span data-ttu-id="4e393-116">Wartości sekwencji `ulParamSeq` zaczynają się od 1 dla parametrów.</span><span class="sxs-lookup"><span data-stu-id="4e393-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="4e393-117">Wartość zwracana ma numer sekwencyjny równy 0.</span><span class="sxs-lookup"><span data-stu-id="4e393-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e393-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4e393-118">Requirements</span></span>  

 <span data-ttu-id="4e393-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e393-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e393-120">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4e393-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e393-121">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e393-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e393-122">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e393-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e393-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4e393-123">See also</span></span>

- [<span data-ttu-id="4e393-124">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4e393-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="4e393-125">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="4e393-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
