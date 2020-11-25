---
title: ICLRMetadataLocator — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
ms.openlocfilehash: 69c52c13a4a0aca5094274de969ebed6e09651b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723509"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="930be-102">ICLRMetadataLocator — Interfejs</span><span class="sxs-lookup"><span data-stu-id="930be-102">ICLRMetadataLocator Interface</span></span>

<span data-ttu-id="930be-103">Używany przez warstwę usług dostępu do danych do lokalizowania metadanych zestawów w procesie docelowym.</span><span class="sxs-lookup"><span data-stu-id="930be-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="930be-104">Metody</span><span class="sxs-lookup"><span data-stu-id="930be-104">Methods</span></span>  
  
|<span data-ttu-id="930be-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="930be-105">Method</span></span>|<span data-ttu-id="930be-106">Opis</span><span class="sxs-lookup"><span data-stu-id="930be-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="930be-107">GetMetadata — Metoda</span><span class="sxs-lookup"><span data-stu-id="930be-107">GetMetadata Method</span></span>](iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="930be-108">Pobiera metadane obrazu z procesu docelowego.</span><span class="sxs-lookup"><span data-stu-id="930be-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="930be-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="930be-109">Remarks</span></span>  

 <span data-ttu-id="930be-110">Klient API (tzn. debuger) musi implementować ten interfejs stosownie do określonego procesu docelowego.</span><span class="sxs-lookup"><span data-stu-id="930be-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="930be-111">Na przykład implementacja procesu na żywo byłaby inna niż w przypadku zrzutu pamięci.</span><span class="sxs-lookup"><span data-stu-id="930be-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="930be-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="930be-112">Requirements</span></span>  

 <span data-ttu-id="930be-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="930be-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="930be-114">**Nagłówek:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="930be-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="930be-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="930be-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="930be-116">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="930be-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="930be-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="930be-117">See also</span></span>

- [<span data-ttu-id="930be-118">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="930be-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
