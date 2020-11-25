---
title: Profiling — Struktury
ms.date: 03/30/2017
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
ms.openlocfilehash: 3f832850fac918a568d02e9ef2f1e5b140ffc04f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722755"
---
# <a name="profiling-structures"></a><span data-ttu-id="0358e-102">Profiling — Struktury</span><span class="sxs-lookup"><span data-stu-id="0358e-102">Profiling Structures</span></span>

<span data-ttu-id="0358e-103">W tej sekcji opisano niezarządzane struktury używane przez interfejs API profilowania.</span><span class="sxs-lookup"><span data-stu-id="0358e-103">This section describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0358e-104">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="0358e-104">In This Section</span></span>  

 [<span data-ttu-id="0358e-105">Struktura COR_PRF_ASSEMBLY_REFERENCE_INFO</span><span class="sxs-lookup"><span data-stu-id="0358e-105">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](cor-prf-assembly-reference-info-structure.md)  
 <span data-ttu-id="0358e-106">Zapewnia środowisko uruchomieniowe języka wspólnego z informacjami o zestawie referencyjnym, które należy wziąć pod uwagę podczas przeprowadzania przeszukiwania odwołań do zestawu.</span><span class="sxs-lookup"><span data-stu-id="0358e-106">Provides the common language runtime with information about a reference assembly that it should consider when performing an assembly reference closure walk.</span></span>  
  
 [<span data-ttu-id="0358e-107">COR_PRF_CODE_INFO — Struktura</span><span class="sxs-lookup"><span data-stu-id="0358e-107">COR_PRF_CODE_INFO Structure</span></span>](cor-prf-code-info-structure.md)  
 <span data-ttu-id="0358e-108">Reprezentuje jeden ciągły blok kodu natywnego przechowywanego w pamięci.</span><span class="sxs-lookup"><span data-stu-id="0358e-108">Represents one contiguous block of native code stored in memory.</span></span>  
  
 [<span data-ttu-id="0358e-109">COR_PRF_EX_CLAUSE_INFO — Struktura</span><span class="sxs-lookup"><span data-stu-id="0358e-109">COR_PRF_EX_CLAUSE_INFO Structure</span></span>](cor-prf-ex-clause-info-structure.md)  
 <span data-ttu-id="0358e-110">Przechowuje informacje o konkretnym wystąpieniu klauzuli wyjątku i skojarzonej z nią ramce.</span><span class="sxs-lookup"><span data-stu-id="0358e-110">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
 [<span data-ttu-id="0358e-111">COR_PRF_FUNCTION — Struktura</span><span class="sxs-lookup"><span data-stu-id="0358e-111">COR_PRF_FUNCTION Structure</span></span>](cor-prf-function-structure.md)  
 <span data-ttu-id="0358e-112">Zapewnia unikatową reprezentację funkcji przez połączenie jej identyfikatora z IDENTYFIKATORem jego ponownie skompilowanej wersji.</span><span class="sxs-lookup"><span data-stu-id="0358e-112">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
 [<span data-ttu-id="0358e-113">COR_PRF_FUNCTION_ARGUMENT_INFO — Struktura</span><span class="sxs-lookup"><span data-stu-id="0358e-113">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>](cor-prf-function-argument-info-structure.md)  
 <span data-ttu-id="0358e-114">Reprezentuje argumenty funkcji w kolejności od lewej do prawej.</span><span class="sxs-lookup"><span data-stu-id="0358e-114">Represents a function's arguments, in left-to-right order.</span></span>  
  
 [<span data-ttu-id="0358e-115">COR_PRF_FUNCTION_ARGUMENT_RANGE — Struktura</span><span class="sxs-lookup"><span data-stu-id="0358e-115">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>](cor-prf-function-argument-range-structure.md)  
 <span data-ttu-id="0358e-116">Reprezentuje blok argumentów funkcji przechowywanych w sposób ciągły w kolejności od lewej do prawej w pamięci.</span><span class="sxs-lookup"><span data-stu-id="0358e-116">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
 [<span data-ttu-id="0358e-117">COR_PRF_GC_GENERATION_RANGE — Struktura</span><span class="sxs-lookup"><span data-stu-id="0358e-117">COR_PRF_GC_GENERATION_RANGE Structure</span></span>](cor-prf-gc-generation-range-structure.md)  
 <span data-ttu-id="0358e-118">Opisuje zakres (czyli blok) pamięci, która jest niedo wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="0358e-118">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0358e-119">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="0358e-119">Related Sections</span></span>  

 <span data-ttu-id="0358e-120">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="0358e-120">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
  
 <span data-ttu-id="0358e-121">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="0358e-121">COR_IL_MAP</span></span>  
  
 [<span data-ttu-id="0358e-122">Omówienie profilowania</span><span class="sxs-lookup"><span data-stu-id="0358e-122">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="0358e-123">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="0358e-123">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="0358e-124">Profilowanie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="0358e-124">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="0358e-125">Profilowanie — Wyliczenia</span><span class="sxs-lookup"><span data-stu-id="0358e-125">Profiling Enumerations</span></span>](profiling-enumerations.md)
