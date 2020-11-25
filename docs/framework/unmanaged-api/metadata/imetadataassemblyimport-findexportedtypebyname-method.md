---
title: IMetaDataAssemblyImport::FindExportedTypeByName — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
ms.openlocfilehash: b1672d98d76241e5af4b6b60a38785f1278e15a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731595"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="dc991-102">IMetaDataAssemblyImport::FindExportedTypeByName — Metoda</span><span class="sxs-lookup"><span data-stu-id="dc991-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>

<span data-ttu-id="dc991-103">Pobiera wskaźnik do wyeksportowanego typu z uwzględnieniem jego nazwy i typu otaczającego.</span><span class="sxs-lookup"><span data-stu-id="dc991-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc991-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="dc991-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc991-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="dc991-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="dc991-106">podczas Nazwa wyeksportowanego typu.</span><span class="sxs-lookup"><span data-stu-id="dc991-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="dc991-107">podczas Token metadanych dla otaczającej klasy wyeksportowanego typu.</span><span class="sxs-lookup"><span data-stu-id="dc991-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="dc991-108">Ta wartość jest `mdExportedTypeNil` , jeśli żądany wyeksportowany typ nie jest typem zagnieżdżonym.</span><span class="sxs-lookup"><span data-stu-id="dc991-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="dc991-109">określoną Wskaźnik do `mdExportedType` tokenu, który reprezentuje wyeksportowany typ.</span><span class="sxs-lookup"><span data-stu-id="dc991-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc991-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dc991-110">Remarks</span></span>  

 <span data-ttu-id="dc991-111">`FindExportedTypeByName`Metoda używa standardowych reguł używanych przez środowisko uruchomieniowe języka wspólnego do rozpoznawania odwołań.</span><span class="sxs-lookup"><span data-stu-id="dc991-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc991-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="dc991-112">Requirements</span></span>  

 <span data-ttu-id="dc991-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc991-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc991-114">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dc991-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc991-115">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dc991-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dc991-116">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc991-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc991-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="dc991-117">See also</span></span>

- [<span data-ttu-id="dc991-118">IMetaDataAssemblyImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="dc991-118">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="dc991-119">Sposoby lokalizowania zestawów przez środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="dc991-119">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
