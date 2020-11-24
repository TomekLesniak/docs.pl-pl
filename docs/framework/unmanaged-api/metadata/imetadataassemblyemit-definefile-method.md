---
title: IMetaDataAssemblyEmit::DefineFile — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
ms.openlocfilehash: 1dd71dbe0ddb894cb5ed05c32e50429d27c66aa2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689332"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="06aea-102">IMetaDataAssemblyEmit::DefineFile — Metoda</span><span class="sxs-lookup"><span data-stu-id="06aea-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>

<span data-ttu-id="06aea-103">Tworzy `File` strukturę metadanych zawierającą metadane zestawu, do którego odwołuje się ten zestaw, i zwraca skojarzony token metadanych.</span><span class="sxs-lookup"><span data-stu-id="06aea-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06aea-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="06aea-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06aea-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="06aea-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="06aea-106">podczas Nazwa pliku, który ma być użyty.</span><span class="sxs-lookup"><span data-stu-id="06aea-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="06aea-107">podczas Wskaźnik do danych skrótu skojarzonych z zestawem.</span><span class="sxs-lookup"><span data-stu-id="06aea-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="06aea-108">podczas Rozmiar w bajtach `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="06aea-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="06aea-109">podczas Bitowa kombinacja `FileFlags` wartości, które określają ustawienia właściwości.</span><span class="sxs-lookup"><span data-stu-id="06aea-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="06aea-110">określoną Wskaźnik do zwracanego `File` tokenu.</span><span class="sxs-lookup"><span data-stu-id="06aea-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06aea-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="06aea-111">Remarks</span></span>  

 <span data-ttu-id="06aea-112">`File`Dla każdego pliku, który był częścią tego zestawu, należy zdefiniować jedną strukturę metadanych, wykluczając plik zawierający metadane.</span><span class="sxs-lookup"><span data-stu-id="06aea-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06aea-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="06aea-113">Requirements</span></span>  

 <span data-ttu-id="06aea-114">**Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06aea-114">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06aea-115">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="06aea-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06aea-116">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06aea-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06aea-117">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06aea-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06aea-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="06aea-118">See also</span></span>

- [<span data-ttu-id="06aea-119">IMetaDataAssemblyEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="06aea-119">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
