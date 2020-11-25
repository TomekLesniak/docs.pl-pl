---
title: ICLRDataTarget2::AllocVirtual — Metoda
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.AllocVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type:
- apiref
ms.openlocfilehash: 6d3985919ea7e766db7d07e4ed81484851156ca5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723672"
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="ac40b-102">ICLRDataTarget2::AllocVirtual — Metoda</span><span class="sxs-lookup"><span data-stu-id="ac40b-102">ICLRDataTarget2::AllocVirtual Method</span></span>

<span data-ttu-id="ac40b-103">Wywoływane przez usługi dostępu do danych środowiska uruchomieniowego języka wspólnego (CLR) do przydzielania pamięci w przestrzeni adresowej tego procesu docelowego.</span><span class="sxs-lookup"><span data-stu-id="ac40b-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac40b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ac40b-104">Syntax</span></span>  
  
```cpp  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac40b-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ac40b-105">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="ac40b-106">podczas Wartość określająca `CLRDATA_ADDRESS` żądany adres początkowy pamięci do przydzielenia.</span><span class="sxs-lookup"><span data-stu-id="ac40b-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="ac40b-107">podczas Rozmiar pamięci do przydzielenia w bajtach.</span><span class="sxs-lookup"><span data-stu-id="ac40b-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="ac40b-108">podczas Flagi kontrolujące przydział pamięci.</span><span class="sxs-lookup"><span data-stu-id="ac40b-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="ac40b-109">Zobacz funkcję Win32 `VirtualAlloc` .</span><span class="sxs-lookup"><span data-stu-id="ac40b-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="ac40b-110">podczas Atrybuty ochrony przydzieloną pamięć.</span><span class="sxs-lookup"><span data-stu-id="ac40b-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="ac40b-111">Zobacz funkcję Win32 `VirtualAlloc` .</span><span class="sxs-lookup"><span data-stu-id="ac40b-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="ac40b-112">określoną Wskaźnik do `CLRDATA_ADDRESS` wartości, która określa rzeczywisty adres początkowy przydzieloną pamięć.</span><span class="sxs-lookup"><span data-stu-id="ac40b-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac40b-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ac40b-113">Remarks</span></span>  

 <span data-ttu-id="ac40b-114">`AllocVirtual`Metoda służy jako otoka logiczna dla `VirtualAlloc` funkcji Win32.</span><span class="sxs-lookup"><span data-stu-id="ac40b-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="ac40b-115">Ta metoda jest implementowana przez moduł zapisujący aplikacji debugowania.</span><span class="sxs-lookup"><span data-stu-id="ac40b-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac40b-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ac40b-116">Requirements</span></span>  

 <span data-ttu-id="ac40b-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac40b-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac40b-118">**Nagłówek:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="ac40b-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ac40b-119">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ac40b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac40b-120">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac40b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac40b-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ac40b-121">See also</span></span>

- [<span data-ttu-id="ac40b-122">ICLRDataTarget2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ac40b-122">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="ac40b-123">FreeVirtual, metoda</span><span class="sxs-lookup"><span data-stu-id="ac40b-123">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)
