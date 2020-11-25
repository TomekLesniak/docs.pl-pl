---
title: IMetaDataEmit::TranslateSigWithScope — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
ms.openlocfilehash: 80d33da2eb2a7f0cfbe5dcb7279fff9973dada2e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712927"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="fd2ac-102">IMetaDataEmit::TranslateSigWithScope — Metoda</span><span class="sxs-lookup"><span data-stu-id="fd2ac-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>

<span data-ttu-id="fd2ac-103">Importuje zestaw do bieżącego zakresu i pobiera nowy podpis metadanych dla scalonego zakresu.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd2ac-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fd2ac-104">Syntax</span></span>  
  
```cpp  
HRESULT TranslateSigWithScope (
    [in]  IMetaDataAssemblyImport   *pAssemImport,
    [in]  const void                *pbHashValue,
    [in]  ULONG                     cbHashValue,
    [in]  IMetaDataImport           *import,
    [in]  PCCOR_SIGNATURE           pbSigBlob,
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,
    [in]  IMetaDataEmit             *emit,
    [out] PCOR_SIGNATURE            pvTranslatedSig,
    [in]  ULONG                     cbTranslatedSigMax,
    [out] ULONG                     *pcbTranslatedSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd2ac-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="fd2ac-105">Parameters</span></span>  

 `pAssemImport`  
 <span data-ttu-id="fd2ac-106">podczas Interfejs dla zestawu importu (gdzie sygnatura jest zdefiniowana).</span><span class="sxs-lookup"><span data-stu-id="fd2ac-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="fd2ac-107">podczas Obiekt BLOB mieszania dla zestawu.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="fd2ac-108">podczas Liczba bajtów w `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="fd2ac-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="fd2ac-109">podczas Interfejs dla zakresu metadanych importu.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="fd2ac-110">podczas Podpis do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="fd2ac-111">podczas Rozmiar, w bajtach, z `pbSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="fd2ac-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="fd2ac-112">podczas Interfejs do eksportowania zestawu.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="fd2ac-113">podczas Interfejs do eksportowania zakresu metadanych.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="fd2ac-114">określoną Bufor do przechowywania przetłumaczonego obiektu BLOB sygnatury.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="fd2ac-115">podczas Pojemność, w bajtach, z `pvTranslatedSig` .</span><span class="sxs-lookup"><span data-stu-id="fd2ac-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="fd2ac-116">określoną Liczba rzeczywistych bajtów w przetłumaczonym podpisie.</span><span class="sxs-lookup"><span data-stu-id="fd2ac-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd2ac-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="fd2ac-117">Requirements</span></span>  

 <span data-ttu-id="fd2ac-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd2ac-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd2ac-119">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fd2ac-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd2ac-120">**Biblioteka:** Używane jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd2ac-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd2ac-121">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd2ac-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd2ac-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="fd2ac-122">See also</span></span>

- [<span data-ttu-id="fd2ac-123">IMetaDataAssemblyEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fd2ac-123">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="fd2ac-124">IMetaDataAssemblyImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fd2ac-124">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="fd2ac-125">IMetaDataEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fd2ac-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="fd2ac-126">IMetaDataEmit2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fd2ac-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="fd2ac-127">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="fd2ac-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
