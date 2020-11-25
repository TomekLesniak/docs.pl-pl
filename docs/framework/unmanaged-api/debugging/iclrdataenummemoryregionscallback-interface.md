---
title: ICLRDataEnumMemoryRegionsCallback — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
ms.openlocfilehash: f080d852b190346740a3629f3b5d46a9f3808293
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703633"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="71236-102">ICLRDataEnumMemoryRegionsCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="71236-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>

<span data-ttu-id="71236-103">Zapewnia metodę wywołania zwrotnego dla [ICLRDataEnumMemoryRegions:: EnumMemoryRegions —](iclrdataenummemoryregions-enummemoryregions-method.md) , aby zgłosić do debugera wynik próby wyliczenia określonego regionu pamięci.</span><span class="sxs-lookup"><span data-stu-id="71236-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="71236-104">Metody</span><span class="sxs-lookup"><span data-stu-id="71236-104">Methods</span></span>  
  
|<span data-ttu-id="71236-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="71236-105">Method</span></span>|<span data-ttu-id="71236-106">Opis</span><span class="sxs-lookup"><span data-stu-id="71236-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="71236-107">EnumMemoryRegion, metoda</span><span class="sxs-lookup"><span data-stu-id="71236-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="71236-108">Wywołuje `ICLRDataEnumMemoryRegions::EnumMemoryRegions` się, by zgłosić debugerowi wynik próby wyliczenia określonego regionu pamięci.</span><span class="sxs-lookup"><span data-stu-id="71236-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71236-109">Wymagania</span><span class="sxs-lookup"><span data-stu-id="71236-109">Requirements</span></span>  

 <span data-ttu-id="71236-110">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71236-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71236-111">**Nagłówek:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="71236-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="71236-112">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="71236-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71236-113">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71236-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71236-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="71236-114">See also</span></span>

- [<span data-ttu-id="71236-115">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="71236-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
