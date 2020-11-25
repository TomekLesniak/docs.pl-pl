---
title: IMetaDataAssemblyImport::EnumAssemblyRefs — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
ms.openlocfilehash: 18cd9dd14e615a7e76bfff30c9ae584305bd1907
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708944"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="a6749-102">IMetaDataAssemblyImport::EnumAssemblyRefs — Metoda</span><span class="sxs-lookup"><span data-stu-id="a6749-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>

<span data-ttu-id="a6749-103">Wylicza `mdAssemblyRef` wystąpienia, które są zdefiniowane w manifeście zestawu.</span><span class="sxs-lookup"><span data-stu-id="a6749-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6749-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a6749-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6749-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a6749-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="a6749-106">[in. out] Wskaźnik do modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="a6749-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a6749-107">Ta wartość musi być wartością null, gdy `EnumAssemblyRefs` Metoda jest wywoływana po raz pierwszy.</span><span class="sxs-lookup"><span data-stu-id="a6749-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="a6749-108">określoną Wyliczanie `mdAssemblyRef` tokenów metadanych.</span><span class="sxs-lookup"><span data-stu-id="a6749-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a6749-109">podczas Maksymalna liczba tokenów, które mogą zostać umieszczone w `rAssemblyRefs` tablicy.</span><span class="sxs-lookup"><span data-stu-id="a6749-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a6749-110">określoną Liczba tokenów, które zostały umieszczone w rzeczywistości `rAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="a6749-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6749-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="a6749-111">Return Value</span></span>  
  
|<span data-ttu-id="a6749-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a6749-112">HRESULT</span></span>|<span data-ttu-id="a6749-113">Opis</span><span class="sxs-lookup"><span data-stu-id="a6749-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a6749-114">`EnumAssemblyRefs` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="a6749-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a6749-115">Brak tokenów do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="a6749-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a6749-116">W tym przypadku `pcTokens` jest ustawiona na zero.</span><span class="sxs-lookup"><span data-stu-id="a6749-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6749-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a6749-117">Requirements</span></span>  

 <span data-ttu-id="a6749-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6749-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6749-119">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a6749-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6749-120">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6749-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6749-121">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6749-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6749-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a6749-122">See also</span></span>

- [<span data-ttu-id="a6749-123">IMetaDataAssemblyImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a6749-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
