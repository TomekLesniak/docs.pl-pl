---
title: IMetaDataImport::GetScopeProps — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
ms.openlocfilehash: 5a89d1406daa9a2416a708b63d88fd9005234015
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729203"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="83daf-102">IMetaDataImport::GetScopeProps — Metoda</span><span class="sxs-lookup"><span data-stu-id="83daf-102">IMetaDataImport::GetScopeProps Method</span></span>

<span data-ttu-id="83daf-103">Pobiera nazwę i opcjonalnie identyfikator wersji zestawu lub modułu w bieżącym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="83daf-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83daf-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="83daf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83daf-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="83daf-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="83daf-106">określoną Bufor dla nazwy zestawu lub modułu.</span><span class="sxs-lookup"><span data-stu-id="83daf-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="83daf-107">podczas Rozmiar w postaci znaków dwubajtowych `szName` .</span><span class="sxs-lookup"><span data-stu-id="83daf-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="83daf-108">określoną Liczba znaków dwubajtowych zwracana w `szName` .</span><span class="sxs-lookup"><span data-stu-id="83daf-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="83daf-109">[out, opcjonalne] Wskaźnik do identyfikatora GUID, który jednoznacznie identyfikuje wersję zestawu lub modułu.</span><span class="sxs-lookup"><span data-stu-id="83daf-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83daf-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="83daf-110">Remarks</span></span>  

 <span data-ttu-id="83daf-111">Metoda [IMetaDataEmit:: SetModuleProps —](imetadataemit-setmoduleprops-method.md) służy do ustawiania tych właściwości.</span><span class="sxs-lookup"><span data-stu-id="83daf-111">The [IMetaDataEmit::SetModuleProps](imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83daf-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="83daf-112">Requirements</span></span>  

 <span data-ttu-id="83daf-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83daf-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83daf-114">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="83daf-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83daf-115">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="83daf-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="83daf-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83daf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83daf-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="83daf-117">See also</span></span>

- [<span data-ttu-id="83daf-118">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="83daf-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="83daf-119">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="83daf-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
