---
title: ICLRDataTarget2 — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
ms.openlocfilehash: dee5108439610b67c3397cebcd8ee5f84d4eacea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723639"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="41f64-102">ICLRDataTarget2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="41f64-102">ICLRDataTarget2 Interface</span></span>

<span data-ttu-id="41f64-103">Podklasa elementu [ICLRDataTarget](iclrdatatarget-interface.md) , która jest używana przez warstwę usług dostępu do danych do manipulowania regionami pamięci wirtualnej w procesie docelowym.</span><span class="sxs-lookup"><span data-stu-id="41f64-103">A subclass of [ICLRDataTarget](iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="41f64-104">Metody</span><span class="sxs-lookup"><span data-stu-id="41f64-104">Methods</span></span>  
  
|<span data-ttu-id="41f64-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="41f64-105">Method</span></span>|<span data-ttu-id="41f64-106">Opis</span><span class="sxs-lookup"><span data-stu-id="41f64-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41f64-107">AllocVirtual, metoda</span><span class="sxs-lookup"><span data-stu-id="41f64-107">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="41f64-108">Przydziela pamięć w przestrzeni adresowej procesu docelowego.</span><span class="sxs-lookup"><span data-stu-id="41f64-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="41f64-109">FreeVirtual, metoda</span><span class="sxs-lookup"><span data-stu-id="41f64-109">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="41f64-110">Zwalnia pamięć, która została wcześniej przypisana w przestrzeni adresowej procesu docelowego.</span><span class="sxs-lookup"><span data-stu-id="41f64-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41f64-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="41f64-111">Remarks</span></span>  

 <span data-ttu-id="41f64-112">Klient API (tzn. debuger) musi implementować ten interfejs stosownie do określonego procesu docelowego.</span><span class="sxs-lookup"><span data-stu-id="41f64-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="41f64-113">Na przykład żywy proces miałby inną implementację od tej ze zrzutu pamięci.</span><span class="sxs-lookup"><span data-stu-id="41f64-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="41f64-114">Cel może nie obsługiwać modyfikacji regionów pamięci.</span><span class="sxs-lookup"><span data-stu-id="41f64-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41f64-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="41f64-115">Requirements</span></span>  

 <span data-ttu-id="41f64-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41f64-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41f64-117">**Nagłówek:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="41f64-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="41f64-118">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="41f64-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41f64-119">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41f64-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41f64-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="41f64-120">See also</span></span>

- [<span data-ttu-id="41f64-121">ICLRDataTarget — Interfejs</span><span class="sxs-lookup"><span data-stu-id="41f64-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="41f64-122">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="41f64-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
