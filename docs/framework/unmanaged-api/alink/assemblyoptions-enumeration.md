---
title: AssemblyOptions — Wyliczenie
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
ms.openlocfilehash: 352e1acd1fdd8297754e18b2e8c6448ea723a557
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717034"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="e60b8-102">AssemblyOptions — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="e60b8-102">AssemblyOptions Enumeration</span></span>

<span data-ttu-id="e60b8-103">Wylicza opcje zestawu.</span><span class="sxs-lookup"><span data-stu-id="e60b8-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e60b8-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="e60b8-104">Syntax</span></span>  
  
```cpp  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a><span data-ttu-id="e60b8-105">Pola</span><span class="sxs-lookup"><span data-stu-id="e60b8-105">Fields</span></span>  
  
|<span data-ttu-id="e60b8-106">Pole</span><span class="sxs-lookup"><span data-stu-id="e60b8-106">Field</span></span>|<span data-ttu-id="e60b8-107">Opis</span><span class="sxs-lookup"><span data-stu-id="e60b8-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e60b8-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="e60b8-108">optAssemTitle</span></span>|<span data-ttu-id="e60b8-109">String — reprezentuje tytuł zestawu.</span><span class="sxs-lookup"><span data-stu-id="e60b8-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="e60b8-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="e60b8-110">optAssemDescription</span></span>|<span data-ttu-id="e60b8-111">Ciąg — zawiera opis zestawu.</span><span class="sxs-lookup"><span data-stu-id="e60b8-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="e60b8-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="e60b8-112">optAssemConfig</span></span>|<span data-ttu-id="e60b8-113">String — zawiera konfigurację zestawu.</span><span class="sxs-lookup"><span data-stu-id="e60b8-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="e60b8-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="e60b8-114">optAssemOS</span></span>|<span data-ttu-id="e60b8-115">Zakodowany ciąg jako: "dwOSPlatformId. dwOSMajorVersion. dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="e60b8-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="e60b8-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="e60b8-116">optAssemProcessor</span></span>|<span data-ttu-id="e60b8-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="e60b8-117">ULONG</span></span>|  
|<span data-ttu-id="e60b8-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="e60b8-118">optAssemLocale</span></span>|<span data-ttu-id="e60b8-119">Ciąg — zawiera ustawienia regionalne zestawu.</span><span class="sxs-lookup"><span data-stu-id="e60b8-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="e60b8-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="e60b8-120">optAssemVersion</span></span>|<span data-ttu-id="e60b8-121">Zakodowany ciąg jako: "główna. pomocnicza. kompilacja. poprawka".</span><span class="sxs-lookup"><span data-stu-id="e60b8-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="e60b8-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="e60b8-122">optAssemCompany</span></span>|<span data-ttu-id="e60b8-123">Ciąg — zawiera firmę.</span><span class="sxs-lookup"><span data-stu-id="e60b8-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="e60b8-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="e60b8-124">optAssemProduct</span></span>|<span data-ttu-id="e60b8-125">String — zawiera nazwę produktu.</span><span class="sxs-lookup"><span data-stu-id="e60b8-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="e60b8-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="e60b8-126">optAssemProductVersion</span></span>|<span data-ttu-id="e60b8-127">Ciąg (znany również jako InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="e60b8-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="e60b8-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="e60b8-128">optAssemCopyright</span></span>|<span data-ttu-id="e60b8-129">Ciąg — zawiera informacje o prawach autorskich.</span><span class="sxs-lookup"><span data-stu-id="e60b8-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="e60b8-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="e60b8-130">optAssemTrademark</span></span>|<span data-ttu-id="e60b8-131">Ciąg — zawiera informacje o znakach towarowych.</span><span class="sxs-lookup"><span data-stu-id="e60b8-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="e60b8-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="e60b8-132">optAssemKeyFile</span></span>|<span data-ttu-id="e60b8-133">Ciąg (nazwa pliku).</span><span class="sxs-lookup"><span data-stu-id="e60b8-133">String (file name).</span></span>|  
|<span data-ttu-id="e60b8-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="e60b8-134">optAssemKeyName</span></span>|<span data-ttu-id="e60b8-135">Ciąg (nazwa klucza).</span><span class="sxs-lookup"><span data-stu-id="e60b8-135">String (The key name).</span></span>|  
|<span data-ttu-id="e60b8-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="e60b8-136">optAssemAlgID</span></span>|<span data-ttu-id="e60b8-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="e60b8-137">ULONG</span></span>|  
|<span data-ttu-id="e60b8-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="e60b8-138">optAssemFlags</span></span>|<span data-ttu-id="e60b8-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="e60b8-139">ULONG</span></span>|  
|<span data-ttu-id="e60b8-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="e60b8-140">optAssemHalfSign</span></span>|<span data-ttu-id="e60b8-141">Bool (znany również jako DelaySign).</span><span class="sxs-lookup"><span data-stu-id="e60b8-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="e60b8-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="e60b8-142">optAssemFileVersion</span></span>|<span data-ttu-id="e60b8-143">Zakodowana ciągowo jako "główna. pomocnicza. kompilacja. poprawka" — taka sama jak ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="e60b8-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="e60b8-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="e60b8-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="e60b8-145">Kodowanie ciągu jako "główna. pomocnicza. kompilacja. poprawka".</span><span class="sxs-lookup"><span data-stu-id="e60b8-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="e60b8-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="e60b8-146">optLastAssemOption</span></span>|<span data-ttu-id="e60b8-147">Licznik liczby elementów.</span><span class="sxs-lookup"><span data-stu-id="e60b8-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e60b8-148">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e60b8-148">Requirements</span></span>  

 <span data-ttu-id="e60b8-149">**Nagłówek:** Alink. h</span><span class="sxs-lookup"><span data-stu-id="e60b8-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="e60b8-150">**Biblioteka**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="e60b8-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e60b8-151">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e60b8-151">See also</span></span>

- [<span data-ttu-id="e60b8-152">Al.exe (Konsolidator zestawu)</span><span class="sxs-lookup"><span data-stu-id="e60b8-152">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
