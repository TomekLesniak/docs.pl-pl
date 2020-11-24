---
title: ICLRDataEnumMemoryRegions::EnumMemoryRegions — Metoda
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
ms.openlocfilehash: 386f975ab0bbbe804fda2bd7567acf24f69e77fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676078"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="d0b1c-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions — Metoda</span><span class="sxs-lookup"><span data-stu-id="d0b1c-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>

<span data-ttu-id="d0b1c-103">Wylicza określone obszary pamięci.</span><span class="sxs-lookup"><span data-stu-id="d0b1c-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0b1c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="d0b1c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0b1c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="d0b1c-105">Parameters</span></span>  

 `callback`  
 <span data-ttu-id="d0b1c-106">podczas Wskaźnik do wystąpienia [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) , który jest wywoływany przez tę metodę dla każdego regionu pamięci, który jest wyliczany w celu powiadomienia debugera wyniku.</span><span class="sxs-lookup"><span data-stu-id="d0b1c-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="d0b1c-107">Wyliczenie regionów pamięci jest kontynuowane nawet wtedy, gdy wywołanie zwrotne wskazuje na błąd.</span><span class="sxs-lookup"><span data-stu-id="d0b1c-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="d0b1c-108">podczas Nieużywane.</span><span class="sxs-lookup"><span data-stu-id="d0b1c-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="d0b1c-109">podczas Wartość wyliczenia [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) , która określa regiony pamięci do wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="d0b1c-109">[in] A value of the [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0b1c-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d0b1c-110">Remarks</span></span>  

 <span data-ttu-id="d0b1c-111">Ta metoda używa określonego wystąpienia [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) do powiadomienia obiektu wywołującego wyniki.</span><span class="sxs-lookup"><span data-stu-id="d0b1c-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0b1c-112">Wymagania</span><span class="sxs-lookup"><span data-stu-id="d0b1c-112">Requirements</span></span>  

 <span data-ttu-id="d0b1c-113">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0b1c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0b1c-114">**Nagłówek:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="d0b1c-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d0b1c-115">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="d0b1c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0b1c-116">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0b1c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0b1c-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d0b1c-117">See also</span></span>

- [<span data-ttu-id="d0b1c-118">ICLRDataEnumMemoryRegions — Interfejs</span><span class="sxs-lookup"><span data-stu-id="d0b1c-118">ICLRDataEnumMemoryRegions Interface</span></span>](iclrdataenummemoryregions-interface.md)
