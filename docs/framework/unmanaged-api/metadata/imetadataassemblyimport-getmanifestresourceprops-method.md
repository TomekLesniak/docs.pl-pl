---
title: IMetaDataAssemblyImport::GetManifestResourceProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: 585a9e39f529294841cd11389f03d763968a0f5e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723821"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="b91d5-102">IMetaDataAssemblyImport::GetManifestResourceProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="b91d5-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>

<span data-ttu-id="b91d5-103">Pobiera zestaw właściwości zasobu manifestu z określonym podpisem metadanych.</span><span class="sxs-lookup"><span data-stu-id="b91d5-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b91d5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b91d5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] mdToken              *ptkImplementation,
    [out] DWORD                *pdwOffset,
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b91d5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="b91d5-105">Parameters</span></span>  

 `mdmr`  
 <span data-ttu-id="b91d5-106">podczas `mdManifestResource` Token reprezentujący zasób, dla którego mają zostać pobrane właściwości.</span><span class="sxs-lookup"><span data-stu-id="b91d5-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="b91d5-107">określoną Nazwa zasobu.</span><span class="sxs-lookup"><span data-stu-id="b91d5-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="b91d5-108">podczas Rozmiar, w postaci szerokich znaków, z `szName` .</span><span class="sxs-lookup"><span data-stu-id="b91d5-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="b91d5-109">określoną Wskaźnik do liczby znaków dwubajtowych faktycznie zwróconych w `szName` .</span><span class="sxs-lookup"><span data-stu-id="b91d5-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="b91d5-110">określoną Wskaźnik do `mdFile` tokenu lub `mdAssemblyRef` tokenu, który reprezentuje odpowiednio plik lub zestaw, który zawiera zasób.</span><span class="sxs-lookup"><span data-stu-id="b91d5-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="b91d5-111">określoną Wskaźnik do wartości, która określa przesunięcie do początku zasobu w pliku.</span><span class="sxs-lookup"><span data-stu-id="b91d5-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="b91d5-112">określoną Wskaźnik do flag, które opisują metadane zastosowane do zasobu.</span><span class="sxs-lookup"><span data-stu-id="b91d5-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="b91d5-113">Wartość flags jest kombinacją co najmniej jednej wartości [CorManifestResourceFlags —](cormanifestresourceflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b91d5-113">The flags value is a combination of one or more [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b91d5-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b91d5-114">Requirements</span></span>  

 <span data-ttu-id="b91d5-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b91d5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b91d5-116">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b91d5-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b91d5-117">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b91d5-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b91d5-118">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b91d5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b91d5-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="b91d5-119">See also</span></span>

- [<span data-ttu-id="b91d5-120">IMetaDataAssemblyImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="b91d5-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
