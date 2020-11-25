---
title: IMetaDataAssemblyImport::FindManifestResourceByName — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
ms.openlocfilehash: 152f62fddee3eaa7fa14e454e6eb7ea2547265ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731582"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="df9f5-102">IMetaDataAssemblyImport::FindManifestResourceByName — Metoda</span><span class="sxs-lookup"><span data-stu-id="df9f5-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>

<span data-ttu-id="df9f5-103">Pobiera wskaźnik do zasobu manifestu o podanej nazwie.</span><span class="sxs-lookup"><span data-stu-id="df9f5-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df9f5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="df9f5-104">Syntax</span></span>  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,
    [out] mdManifestResource     *ptkManifestResource  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="df9f5-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="df9f5-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="df9f5-106">podczas Nazwa zasobu.</span><span class="sxs-lookup"><span data-stu-id="df9f5-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="df9f5-107">określoną Tablica służąca do przechowywania `mdManifestResource` tokenów metadanych, z których każdy reprezentuje zasób manifestu.</span><span class="sxs-lookup"><span data-stu-id="df9f5-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df9f5-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="df9f5-108">Remarks</span></span>  

 <span data-ttu-id="df9f5-109">`FindManifestResourceByName`Metoda używa standardowych reguł używanych przez środowisko uruchomieniowe języka wspólnego do rozpoznawania odwołań.</span><span class="sxs-lookup"><span data-stu-id="df9f5-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df9f5-110">Wymagania</span><span class="sxs-lookup"><span data-stu-id="df9f5-110">Requirements</span></span>  

 <span data-ttu-id="df9f5-111">**Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df9f5-111">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df9f5-112">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="df9f5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df9f5-113">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df9f5-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="df9f5-114">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df9f5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df9f5-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="df9f5-115">See also</span></span>

- [<span data-ttu-id="df9f5-116">IMetaDataAssemblyImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="df9f5-116">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="df9f5-117">Sposoby lokalizowania zestawów przez środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="df9f5-117">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
