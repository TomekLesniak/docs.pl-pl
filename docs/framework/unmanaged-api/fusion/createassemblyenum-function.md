---
title: CreateAssemblyEnum — Funkcja
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
ms.openlocfilehash: b7e3696121475885f5061bd96eb6905d7ccae734
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683176"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="ef199-102">CreateAssemblyEnum — Funkcja</span><span class="sxs-lookup"><span data-stu-id="ef199-102">CreateAssemblyEnum Function</span></span>

<span data-ttu-id="ef199-103">Pobiera wskaźnik do wystąpienia [IAssemblyEnum](iassemblyenum-interface.md) , które może wyliczyć obiekty w zestawie przy użyciu określonego [IAssemblyName](iassemblyname-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ef199-103">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef199-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ef199-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef199-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="ef199-105">Parameters</span></span>  

 `pEnum`  
 <span data-ttu-id="ef199-106">określoną Wskaźnik do lokalizacji pamięci, która zawiera żądany `IAssemblyEnum` wskaźnik.</span><span class="sxs-lookup"><span data-stu-id="ef199-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="ef199-107">podczas Zarezerwowane do użytku w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="ef199-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ef199-108">`pUnkReserved` musi być odwołaniem o wartości null.</span><span class="sxs-lookup"><span data-stu-id="ef199-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="ef199-109">podczas `IAssemblyName` Żądanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="ef199-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="ef199-110">Ta nazwa jest używana do filtrowania wyliczania.</span><span class="sxs-lookup"><span data-stu-id="ef199-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="ef199-111">Może ona mieć wartość null, aby wyliczyć wszystkie zestawy w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="ef199-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ef199-112">podczas Flagi modyfikujące zachowanie modułu wyliczającego.</span><span class="sxs-lookup"><span data-stu-id="ef199-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="ef199-113">Ten parametr zawiera dokładnie jeden bit z wyliczenia [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ef199-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="ef199-114">podczas Zarezerwowane do użytku w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="ef199-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ef199-115">`pvReserved` musi być odwołaniem o wartości null.</span><span class="sxs-lookup"><span data-stu-id="ef199-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef199-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ef199-116">Remarks</span></span>  

 <span data-ttu-id="ef199-117">`dwFlags`Parametr zawiera dokładnie jeden bit z `ASM_CACHE_FLAGS` wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="ef199-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef199-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="ef199-118">Requirements</span></span>  

 <span data-ttu-id="ef199-119">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef199-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef199-120">**Nagłówek:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ef199-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ef199-121">**Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef199-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ef199-122">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef199-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef199-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ef199-123">See also</span></span>

- [<span data-ttu-id="ef199-124">IAssemblyEnum — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ef199-124">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
- [<span data-ttu-id="ef199-125">IAssemblyName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="ef199-125">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="ef199-126">Łączenie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="ef199-126">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
