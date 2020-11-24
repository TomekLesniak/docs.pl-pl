---
title: ICorProfilerInfo7, interfejs
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 4acafafa284549fe1b078542a88c0818dcde3038
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686062"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="3c344-102">ICorProfilerInfo7, interfejs</span><span class="sxs-lookup"><span data-stu-id="3c344-102">ICorProfilerInfo7 Interface</span></span>

<span data-ttu-id="3c344-103">[Obsługiwane w .NET Framework 4.6.1 i nowszych wersjach]</span><span class="sxs-lookup"><span data-stu-id="3c344-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="3c344-104">Podklasa elementu [ICorProfilerInfo6](icorprofilerinfo6-interface.md) , która zapewnia metodę zastosowania nowo zdefiniowanych metadanych do modułu i zapewnia dostęp do strumienia symboli w pamięci.</span><span class="sxs-lookup"><span data-stu-id="3c344-104">A subclass of [ICorProfilerInfo6](icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3c344-105">Metody</span><span class="sxs-lookup"><span data-stu-id="3c344-105">Methods</span></span>  
  
|<span data-ttu-id="3c344-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="3c344-106">Method</span></span>|<span data-ttu-id="3c344-107">Opis</span><span class="sxs-lookup"><span data-stu-id="3c344-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3c344-108">ApplyMetaData, metoda</span><span class="sxs-lookup"><span data-stu-id="3c344-108">ApplyMetaData Method</span></span>](icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="3c344-109">Stosuje metadane nowo zdefiniowane przez `IMetadataEmit::Define*` metody do określonego modułu.</span><span class="sxs-lookup"><span data-stu-id="3c344-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="3c344-110">GetInMemorySymbolsLength, metoda</span><span class="sxs-lookup"><span data-stu-id="3c344-110">GetInMemorySymbolsLength Method</span></span>](icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="3c344-111">Zwraca długość strumienia symboli w pamięci.</span><span class="sxs-lookup"><span data-stu-id="3c344-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="3c344-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="3c344-112">ReadInMemorySymbols</span></span>](icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="3c344-113">Odczytuje bajty z strumienia symboli w pamięci.</span><span class="sxs-lookup"><span data-stu-id="3c344-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c344-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="3c344-114">Requirements</span></span>  

 <span data-ttu-id="3c344-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c344-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c344-116">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="3c344-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3c344-117">**.NET Framework wersje:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c344-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c344-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3c344-118">See also</span></span>

- [<span data-ttu-id="3c344-119">Interfejsy profilowania</span><span class="sxs-lookup"><span data-stu-id="3c344-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
