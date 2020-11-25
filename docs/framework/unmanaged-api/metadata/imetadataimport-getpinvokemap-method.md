---
title: IMetaDataImport::GetPinvokeMap — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
ms.openlocfilehash: c34215f48190e60bd1a851f31b8b23f09491f4e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729242"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="154b2-102">IMetaDataImport::GetPinvokeMap — Metoda</span><span class="sxs-lookup"><span data-stu-id="154b2-102">IMetaDataImport::GetPinvokeMap Method</span></span>

<span data-ttu-id="154b2-103">Pobiera token typu ModuleRef reprezentujący zestaw docelowy wywołania PInvoke.</span><span class="sxs-lookup"><span data-stu-id="154b2-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="154b2-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="154b2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="154b2-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="154b2-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="154b2-106">podczas Token FieldDef lub MethodDef, aby uzyskać metadane mapowania funkcji PInvoke dla.</span><span class="sxs-lookup"><span data-stu-id="154b2-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="154b2-107">określoną Wskaźnik do flag użytych do mapowania.</span><span class="sxs-lookup"><span data-stu-id="154b2-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="154b2-108">Ta wartość jest maska bitowa z wyliczenia [CorPinvokeMap —](corpinvokemap-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="154b2-108">This value is a bitmask from the [CorPinvokeMap](corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="154b2-109">określoną Nazwa niezarządzanej docelowej biblioteki DLL.</span><span class="sxs-lookup"><span data-stu-id="154b2-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="154b2-110">podczas Rozmiar w postaci znaków dwubajtowych `szImportName` .</span><span class="sxs-lookup"><span data-stu-id="154b2-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="154b2-111">określoną Liczba znaków dwubajtowych zwracana w `szImportName` .</span><span class="sxs-lookup"><span data-stu-id="154b2-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="154b2-112">określoną Wskaźnik do tokenu elementu ModuleRef, który reprezentuje niezarządzaną bibliotekę obiektów docelowych.</span><span class="sxs-lookup"><span data-stu-id="154b2-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="154b2-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="154b2-113">Requirements</span></span>  

 <span data-ttu-id="154b2-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="154b2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="154b2-115">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="154b2-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="154b2-116">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="154b2-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="154b2-117">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="154b2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="154b2-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="154b2-118">See also</span></span>

- [<span data-ttu-id="154b2-119">IMetaDataImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="154b2-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="154b2-120">IMetaDataImport2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="154b2-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
