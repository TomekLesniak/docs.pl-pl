---
title: IMetaDataImport::GetTypeRefProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
ms.openlocfilehash: 5d98481d7934b4c96178aaa32fb0f9378eb359fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729175"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="1254b-102">IMetaDataImport::GetTypeRefProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="1254b-102">IMetaDataImport::GetTypeRefProps Method</span></span>

<span data-ttu-id="1254b-103">Pobiera metadane skojarzone z <xref:System.Type> przywoływanym przez określony tokenem elementu TypeRef.</span><span class="sxs-lookup"><span data-stu-id="1254b-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1254b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1254b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1254b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="1254b-105">Parameters</span></span>  

 `tr`  
 <span data-ttu-id="1254b-106">podczas Token elementu TypeRef, który reprezentuje typ do zwrócenia metadanych.</span><span class="sxs-lookup"><span data-stu-id="1254b-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="1254b-107">określoną Wskaźnik do zakresu, w którym następuje odwołanie.</span><span class="sxs-lookup"><span data-stu-id="1254b-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="1254b-108">Ta wartość jest tokenem AssemblyRef lub ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="1254b-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="1254b-109">określoną Bufor zawierający nazwę typu.</span><span class="sxs-lookup"><span data-stu-id="1254b-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="1254b-110">podczas Żądany rozmiar w postaci znaków dwubajtowych `szName` .</span><span class="sxs-lookup"><span data-stu-id="1254b-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="1254b-111">określoną Zwrócony rozmiar w postaci znaków dwubajtowych `szName` .</span><span class="sxs-lookup"><span data-stu-id="1254b-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1254b-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="1254b-112">Requirements</span></span>  

 <span data-ttu-id="1254b-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1254b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1254b-114">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1254b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1254b-115">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1254b-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1254b-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1254b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1254b-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="1254b-117">See also</span></span>

- [<span data-ttu-id="1254b-118">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="1254b-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1254b-119">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="1254b-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
