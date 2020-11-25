---
title: IMetaDataAssemblyImport — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
ms.openlocfilehash: c556fe247754b363ece0c5dc60750068276ddcc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714760"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="9381c-102">IMetaDataAssemblyImport — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9381c-102">IMetaDataAssemblyImport Interface</span></span>

<span data-ttu-id="9381c-103">Zapewnia metody umożliwiające dostęp i sprawdzanie zawartości manifestu zestawu.</span><span class="sxs-lookup"><span data-stu-id="9381c-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9381c-104">Metody</span><span class="sxs-lookup"><span data-stu-id="9381c-104">Methods</span></span>  
  
|<span data-ttu-id="9381c-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-105">Method</span></span>|<span data-ttu-id="9381c-106">Opis</span><span class="sxs-lookup"><span data-stu-id="9381c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9381c-107">CloseEnum — Metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-107">CloseEnum Method</span></span>](imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="9381c-108">Zwalnia dojście do określonego modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="9381c-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="9381c-109">EnumAssemblyRefs, metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-109">EnumAssemblyRefs Method</span></span>](imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="9381c-110">Pobiera wskaźnik interfejsu do modułu wyliczającego, który zawiera `mdAssemblyRef` tokeny zestawów, do których odwołuje się zestaw w bieżącym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="9381c-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9381c-111">EnumExportedTypes, metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-111">EnumExportedTypes Method</span></span>](imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="9381c-112">Pobiera wskaźnik interfejsu do modułu wyliczającego, który zawiera `mdExportedType` tokeny typów com, do których odwołuje się zestaw w bieżącym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="9381c-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9381c-113">EnumFiles, metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-113">EnumFiles Method</span></span>](imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="9381c-114">Pobiera wskaźnik interfejsu do modułu wyliczającego, który zawiera `mdFile` tokeny plików, do których odwołuje się zestaw w bieżącym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="9381c-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9381c-115">EnumManifestResources, metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-115">EnumManifestResources Method</span></span>](imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="9381c-116">Pobiera wskaźnik interfejsu do modułu wyliczającego, który zawiera `mdManifestResource` tokeny zasobów, do których odwołuje się zestaw w bieżącym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="9381c-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9381c-117">FindAssembliesByName, metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-117">FindAssembliesByName Method</span></span>](imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="9381c-118">Pobiera tablicę `mdAssemblyRef` tokenów dla zestawów o określonej nazwie.</span><span class="sxs-lookup"><span data-stu-id="9381c-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="9381c-119">FindExportedTypeByName, metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-119">FindExportedTypeByName Method</span></span>](imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="9381c-120">Pobiera `mdExportedType` token dla typu com o określonej nazwie.</span><span class="sxs-lookup"><span data-stu-id="9381c-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="9381c-121">FindManifestResourceByName, metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-121">FindManifestResourceByName Method</span></span>](imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="9381c-122">Pobiera `mdManifestResource` token dla zasobu o określonej nazwie.</span><span class="sxs-lookup"><span data-stu-id="9381c-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="9381c-123">GetAssemblyFromScope, metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-123">GetAssemblyFromScope Method</span></span>](imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="9381c-124">Pobiera token dla zestawu w bieżącym zakresie metadanych.</span><span class="sxs-lookup"><span data-stu-id="9381c-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="9381c-125">GetAssemblyProps, metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-125">GetAssemblyProps Method</span></span>](imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="9381c-126">Pobiera ustawienia właściwości określonego zestawu.</span><span class="sxs-lookup"><span data-stu-id="9381c-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="9381c-127">GetAssemblyRefProps, metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-127">GetAssemblyRefProps Method</span></span>](imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="9381c-128">Pobiera ustawienia właściwości określonego `mdAssemblyRef` tokenu.</span><span class="sxs-lookup"><span data-stu-id="9381c-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="9381c-129">GetExportedTypeProps, metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-129">GetExportedTypeProps Method</span></span>](imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="9381c-130">Pobiera ustawienia właściwości określonego typu COM.</span><span class="sxs-lookup"><span data-stu-id="9381c-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="9381c-131">GetFileProps, metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-131">GetFileProps Method</span></span>](imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="9381c-132">Pobiera ustawienia właściwości określonego pliku.</span><span class="sxs-lookup"><span data-stu-id="9381c-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="9381c-133">GetManifestResourceProps, metoda</span><span class="sxs-lookup"><span data-stu-id="9381c-133">GetManifestResourceProps Method</span></span>](imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="9381c-134">Pobiera ustawienia właściwości określonego zasobu manifestu.</span><span class="sxs-lookup"><span data-stu-id="9381c-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9381c-135">Wymagania</span><span class="sxs-lookup"><span data-stu-id="9381c-135">Requirements</span></span>  

 <span data-ttu-id="9381c-136">**Platforma:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9381c-136">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9381c-137">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9381c-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9381c-138">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9381c-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9381c-139">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9381c-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9381c-140">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9381c-140">See also</span></span>

- [<span data-ttu-id="9381c-141">Interfejsy metadanych</span><span class="sxs-lookup"><span data-stu-id="9381c-141">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="9381c-142">IMetaDataAssemblyEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="9381c-142">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
