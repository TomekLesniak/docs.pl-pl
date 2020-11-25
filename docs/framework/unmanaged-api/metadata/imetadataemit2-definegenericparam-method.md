---
title: IMetaDataEmit2::DefineGenericParam — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
ms.openlocfilehash: c9ff918121e7bb4ee972e674207810358b3f36f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712914"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="55a63-102">IMetaDataEmit2::DefineGenericParam — Metoda</span><span class="sxs-lookup"><span data-stu-id="55a63-102">IMetaDataEmit2::DefineGenericParam Method</span></span>

<span data-ttu-id="55a63-103">Tworzy definicję parametru typu ogólnego i pobiera token do tego parametru typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="55a63-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55a63-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="55a63-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGenericParam (
    [in]  mdToken         tk,
    [in]  ULONG           ulParamSeq,
    [in]  DWORD           dwParamFlags,
    [in]  LPCWSTR         szname,
    [in]  DWORD           reserved,
    [in]  mdToken         rtkConstraints[],
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55a63-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="55a63-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="55a63-106">podczas `mdTypeDef` Token lub `mdMethodDef` reprezentujący metodę lub konstruktora, dla którego ma zostać zdefiniowany parametr generyczny.</span><span class="sxs-lookup"><span data-stu-id="55a63-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="55a63-107">podczas Indeks parametru generycznego.</span><span class="sxs-lookup"><span data-stu-id="55a63-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="55a63-108">podczas Wartość wyliczenia [CorGenericParamAttr —](corgenericparamattr-enumeration.md) opisująca typ parametru generycznego.</span><span class="sxs-lookup"><span data-stu-id="55a63-108">[in] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="55a63-109">podczas Nazwa parametru.</span><span class="sxs-lookup"><span data-stu-id="55a63-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="55a63-110">podczas Ten parametr jest zarezerwowany do użytku w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="55a63-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="55a63-111">podczas Tablica zakończona zerem z ograniczeniami typu.</span><span class="sxs-lookup"><span data-stu-id="55a63-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="55a63-112">Elementy członkowskie tablicy muszą być `mdTypeDef` `mdTypeRef` `mdTypeSpec` tokenami, lub.</span><span class="sxs-lookup"><span data-stu-id="55a63-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="55a63-113">określoną Token, który reprezentuje parametr generyczny.</span><span class="sxs-lookup"><span data-stu-id="55a63-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55a63-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="55a63-114">Requirements</span></span>  

 <span data-ttu-id="55a63-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55a63-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55a63-116">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="55a63-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="55a63-117">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55a63-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="55a63-118">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55a63-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55a63-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="55a63-119">See also</span></span>

- [<span data-ttu-id="55a63-120">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="55a63-120">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="55a63-121">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="55a63-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
