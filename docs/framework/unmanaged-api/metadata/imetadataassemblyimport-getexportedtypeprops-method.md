---
title: IMetaDataAssemblyImport::GetExportedTypeProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
ms.openlocfilehash: 32224431051b958a3f01ffeb15cdb6db1dae2657
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722105"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="ac4df-102">IMetaDataAssemblyImport::GetExportedTypeProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="ac4df-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>

<span data-ttu-id="ac4df-103">Pobiera zestaw właściwości wyeksportowanego typu z określonym podpisem metadanych.</span><span class="sxs-lookup"><span data-stu-id="ac4df-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac4df-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ac4df-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,
    [out] LPWSTR            szName,
    [in]  ULONG             cchName,
    [out] ULONG             *pchName,
    [out] mdToken           *ptkImplementation,
    [out] mdTypeDef         *ptkTypeDef,
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac4df-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ac4df-105">Parameters</span></span>  

 `mdct`  
 <span data-ttu-id="ac4df-106">podczas `mdExportedType` Token metadanych reprezentujący wyeksportowany typ.</span><span class="sxs-lookup"><span data-stu-id="ac4df-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="ac4df-107">określoną Nazwa wyeksportowanego typu.</span><span class="sxs-lookup"><span data-stu-id="ac4df-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ac4df-108">podczas Rozmiar, w postaci znaków dwubajtowych, z `szName` .</span><span class="sxs-lookup"><span data-stu-id="ac4df-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ac4df-109">określoną Liczba znaków dwubajtowych rzeczywiście zwróconych w `szName`</span><span class="sxs-lookup"><span data-stu-id="ac4df-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="ac4df-110">określoną `mdFile` `mdAssemblyRef` Lub `mdExportedType` token metadanych, który zawiera lub zezwala na dostęp do właściwości wyeksportowanego typu.</span><span class="sxs-lookup"><span data-stu-id="ac4df-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="ac4df-111">określoną Wskaźnik do `mdTypeDef` tokenu, który reprezentuje typ w pliku.</span><span class="sxs-lookup"><span data-stu-id="ac4df-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="ac4df-112">określoną Wskaźnik do flag opisujących metadane zastosowane do wyeksportowanego typu.</span><span class="sxs-lookup"><span data-stu-id="ac4df-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="ac4df-113">Wartość flag może być jedną lub większą liczbą wartości [CorTypeAttr —](cortypeattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ac4df-113">The flags value can be one or more [CorTypeAttr](cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac4df-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ac4df-114">Requirements</span></span>  

 <span data-ttu-id="ac4df-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac4df-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac4df-116">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ac4df-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac4df-117">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac4df-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac4df-118">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac4df-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac4df-119">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ac4df-119">See also</span></span>

- [<span data-ttu-id="ac4df-120">IMetaDataAssemblyImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ac4df-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
