---
title: ASSEMBLYMETADATA — Struktura
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
ms.openlocfilehash: 8071c3f43775975de37e3255582b6fc8f13f7de3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732791"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="474ea-102">ASSEMBLYMETADATA — Struktura</span><span class="sxs-lookup"><span data-stu-id="474ea-102">ASSEMBLYMETADATA Structure</span></span>

<span data-ttu-id="474ea-103">Zawiera informacje o zestawie, do którego istnieje odwołanie, w tym jego wersji oraz o poziomie wsparcia dla ustawień regionalnych, procesorów i systemów operacyjnych.</span><span class="sxs-lookup"><span data-stu-id="474ea-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="474ea-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="474ea-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a><span data-ttu-id="474ea-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="474ea-105">Members</span></span>  
  
|<span data-ttu-id="474ea-106">Członek</span><span class="sxs-lookup"><span data-stu-id="474ea-106">Member</span></span>|<span data-ttu-id="474ea-107">Opis</span><span class="sxs-lookup"><span data-stu-id="474ea-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="474ea-108">Numer wersji głównej przywoływanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="474ea-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="474ea-109">Ta wartość nie może być równa zero.</span><span class="sxs-lookup"><span data-stu-id="474ea-109">This value cannot be zero.</span></span> <span data-ttu-id="474ea-110">Jeśli wszystkie bity `usMajorVersion` są ustawione, wersja główna nie zostanie określona.</span><span class="sxs-lookup"><span data-stu-id="474ea-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="474ea-111">Pomocniczy numer wersji przywoływanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="474ea-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="474ea-112">Ta wartość nie może być równa zero.</span><span class="sxs-lookup"><span data-stu-id="474ea-112">This value cannot be zero.</span></span> <span data-ttu-id="474ea-113">Jeśli wszystkie bity `usMinorVersion` są ustawione, nie zostanie określona wersja pomocnicza.</span><span class="sxs-lookup"><span data-stu-id="474ea-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="474ea-114">Numer kompilacji przywoływanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="474ea-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="474ea-115">Ta wartość nie może być równa zero.</span><span class="sxs-lookup"><span data-stu-id="474ea-115">This value cannot be zero.</span></span> <span data-ttu-id="474ea-116">Jeśli wszystkie bity `usBuildNumber` są ustawione, numer kompilacji nie zostanie określony.</span><span class="sxs-lookup"><span data-stu-id="474ea-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="474ea-117">Numer poprawki przywoływanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="474ea-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="474ea-118">Ta wartość nie może być równa zero.</span><span class="sxs-lookup"><span data-stu-id="474ea-118">This value cannot be zero.</span></span> <span data-ttu-id="474ea-119">Jeśli wszystkie bity `usRevisionNumber` są ustawione, numer poprawki nie zostanie określony.</span><span class="sxs-lookup"><span data-stu-id="474ea-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="474ea-120">Lista nazw ustawień regionalnych zgodna ze specyfikacją RFC1766, oddzielona średnikami, określająca wartości lokalne obsługiwane przez przywoływany zestaw.</span><span class="sxs-lookup"><span data-stu-id="474ea-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="474ea-121">Wartość null wskazuje niezależność ustawień regionalnych.</span><span class="sxs-lookup"><span data-stu-id="474ea-121">A null value indicates locale independence.</span></span> <span data-ttu-id="474ea-122">**Uwaga:**  W .NET Framework w wersji 1,0 nie można określić więcej niż jednego ustawienia regionalnego.</span><span class="sxs-lookup"><span data-stu-id="474ea-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="474ea-123">Rozmiar w postaci znaków dwubajtowych `szLocale` .</span><span class="sxs-lookup"><span data-stu-id="474ea-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="474ea-124">Tablica identyfikatorów, zgodnie z definicją w Winnt. h, dla typów procesorów obsługiwanych przez przywoływany zestaw.</span><span class="sxs-lookup"><span data-stu-id="474ea-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="474ea-125">Wartość NULL wskazuje niezależność procesora.</span><span class="sxs-lookup"><span data-stu-id="474ea-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="474ea-126">Długość `rdwProcessor` tablicy.</span><span class="sxs-lookup"><span data-stu-id="474ea-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="474ea-127">Tablica wystąpień [OSINFO](osinfo-structure.md) określających systemy operacyjne, które są obsługiwane przez przywoływany zestaw.</span><span class="sxs-lookup"><span data-stu-id="474ea-127">An array of [OSINFO](osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="474ea-128">Wartość NULL wskazuje niezależność systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="474ea-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="474ea-129">Długość `rOS` tablicy.</span><span class="sxs-lookup"><span data-stu-id="474ea-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="474ea-130">Wymagania</span><span class="sxs-lookup"><span data-stu-id="474ea-130">Requirements</span></span>  

 <span data-ttu-id="474ea-131">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="474ea-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="474ea-132">**Nagłówek:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="474ea-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="474ea-133">**Biblioteka:** Używane jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="474ea-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="474ea-134">**.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="474ea-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="474ea-135">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="474ea-135">See also</span></span>

- [<span data-ttu-id="474ea-136">Metadane — Struktury</span><span class="sxs-lookup"><span data-stu-id="474ea-136">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="474ea-137">IMetaDataAssemblyEmit — Interfejs</span><span class="sxs-lookup"><span data-stu-id="474ea-137">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="474ea-138">OSINFO — Struktura</span><span class="sxs-lookup"><span data-stu-id="474ea-138">OSINFO Structure</span></span>](osinfo-structure.md)
