---
title: IMetaDataAssemblyImport::EnumExportedTypes — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: a8b2377c48331ff9f0e69876c51fb78c7190f694
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708897"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="62147-102">IMetaDataAssemblyImport::EnumExportedTypes — Metoda</span><span class="sxs-lookup"><span data-stu-id="62147-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>

<span data-ttu-id="62147-103">Wylicza eksportowane typy, do których odwołuje się manifest zestawu w bieżącym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="62147-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62147-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="62147-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62147-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="62147-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="62147-106">[in. out] Wskaźnik do modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="62147-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="62147-107">Ta wartość musi być wartością null, gdy `EnumExportedTypes` Metoda jest wywoływana po raz pierwszy.</span><span class="sxs-lookup"><span data-stu-id="62147-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="62147-108">określoną Wyliczanie `mdExportedType` tokenów metadanych.</span><span class="sxs-lookup"><span data-stu-id="62147-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="62147-109">podczas Maksymalna liczba `mdExportedType` tokenów, które mogą zostać umieszczone w `rExportedTypes` tablicy.</span><span class="sxs-lookup"><span data-stu-id="62147-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="62147-110">określoną Liczba `mdExportedType` tokenów, które zostały umieszczone w rzeczywistości `rExportedTypes` .</span><span class="sxs-lookup"><span data-stu-id="62147-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62147-111">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="62147-111">Return Value</span></span>  
  
|<span data-ttu-id="62147-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62147-112">HRESULT</span></span>|<span data-ttu-id="62147-113">Opis</span><span class="sxs-lookup"><span data-stu-id="62147-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="62147-114">`EnumExportedTypes` pomyślnie zwrócono.</span><span class="sxs-lookup"><span data-stu-id="62147-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="62147-115">Brak tokenów do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="62147-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="62147-116">W tym przypadku `pcTokens` jest ustawiona na zero.</span><span class="sxs-lookup"><span data-stu-id="62147-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="62147-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="62147-117">Requirements</span></span>  

 <span data-ttu-id="62147-118">**Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62147-118">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62147-119">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="62147-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62147-120">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="62147-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62147-121">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62147-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62147-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="62147-122">See also</span></span>

- [<span data-ttu-id="62147-123">IMetaDataAssemblyImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="62147-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
