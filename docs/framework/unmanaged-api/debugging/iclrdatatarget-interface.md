---
title: ICLRDataTarget — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
ms.openlocfilehash: 0d3e6a95d8fd71a67b97923dac53c1f615dfe666
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703424"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="5e892-102">ICLRDataTarget — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5e892-102">ICLRDataTarget Interface</span></span>

<span data-ttu-id="5e892-103">Zapewnia metody interakcji z elementem docelowym środowiska uruchomieniowego języka wspólnego (CLR).</span><span class="sxs-lookup"><span data-stu-id="5e892-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e892-104">Metody</span><span class="sxs-lookup"><span data-stu-id="5e892-104">Methods</span></span>  
  
|<span data-ttu-id="5e892-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="5e892-105">Method</span></span>|<span data-ttu-id="5e892-106">Opis</span><span class="sxs-lookup"><span data-stu-id="5e892-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e892-107">GetCurrentThreadID, metoda</span><span class="sxs-lookup"><span data-stu-id="5e892-107">GetCurrentThreadID Method</span></span>](iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="5e892-108">Pobiera identyfikator systemu operacyjnego dla bieżącego wątku.</span><span class="sxs-lookup"><span data-stu-id="5e892-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="5e892-109">GetImageBase, metoda</span><span class="sxs-lookup"><span data-stu-id="5e892-109">GetImageBase Method</span></span>](iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="5e892-110">Pobiera adres pamięci bazowej dla określonego obrazu.</span><span class="sxs-lookup"><span data-stu-id="5e892-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="5e892-111">GetMachineType, metoda</span><span class="sxs-lookup"><span data-stu-id="5e892-111">GetMachineType Method</span></span>](iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="5e892-112">Pobiera identyfikator rodzaju instrukcji, która jest używana przez proces docelowy.</span><span class="sxs-lookup"><span data-stu-id="5e892-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="5e892-113">GetPointerSize, metoda</span><span class="sxs-lookup"><span data-stu-id="5e892-113">GetPointerSize Method</span></span>](iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="5e892-114">Pobiera rozmiar wskaźnika do bieżącego elementu docelowego w bajtach.</span><span class="sxs-lookup"><span data-stu-id="5e892-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="5e892-115">GetThreadContext, metoda</span><span class="sxs-lookup"><span data-stu-id="5e892-115">GetThreadContext Method</span></span>](iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="5e892-116">Pobiera wskaźnik do kontekstu wątku o określonym identyfikatorze.</span><span class="sxs-lookup"><span data-stu-id="5e892-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="5e892-117">GetTLSValue, metoda</span><span class="sxs-lookup"><span data-stu-id="5e892-117">GetTLSValue Method</span></span>](iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="5e892-118">Pobiera wartość w magazynie lokalnym wątku (TLS) o określonym indeksie dla określonego wątku.</span><span class="sxs-lookup"><span data-stu-id="5e892-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="5e892-119">ReadVirtual, metoda</span><span class="sxs-lookup"><span data-stu-id="5e892-119">ReadVirtual Method</span></span>](iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="5e892-120">Odczytuje dane z określonego adresu pamięci wirtualnej do określonego buforu.</span><span class="sxs-lookup"><span data-stu-id="5e892-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="5e892-121">Request, metoda</span><span class="sxs-lookup"><span data-stu-id="5e892-121">Request Method</span></span>](iclrdatatarget-request-method.md)|<span data-ttu-id="5e892-122">Wywoływane przez usługi dostępu do danych środowiska uruchomieniowego języka wspólnego (CLR) do żądania operacji zgodnie z definicją w implementacji.</span><span class="sxs-lookup"><span data-stu-id="5e892-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="5e892-123">SetThreadContext, metoda</span><span class="sxs-lookup"><span data-stu-id="5e892-123">SetThreadContext Method</span></span>](iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="5e892-124">Ustawia bieżący kontekst określonego wątku w procesie docelowym.</span><span class="sxs-lookup"><span data-stu-id="5e892-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="5e892-125">SetTLSValue, metoda</span><span class="sxs-lookup"><span data-stu-id="5e892-125">SetTLSValue Method</span></span>](iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="5e892-126">Ustawia wartość w ramach wątku lokalnego magazynu (TLS) określonego wątku w procesie docelowym.</span><span class="sxs-lookup"><span data-stu-id="5e892-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="5e892-127">WriteVirtual, metoda</span><span class="sxs-lookup"><span data-stu-id="5e892-127">WriteVirtual Method</span></span>](iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="5e892-128">Zapisuje dane z określonego buforu na określonym adresie pamięci wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="5e892-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e892-129">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5e892-129">Remarks</span></span>  

 <span data-ttu-id="5e892-130">Klient interfejsu API (czyli debuger) musi zaimplementować ten interfejs zgodnie z potrzebami dla określonego elementu docelowego.</span><span class="sxs-lookup"><span data-stu-id="5e892-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="5e892-131">Na przykład żywy proces miałby inną implementację od tej ze zrzutu pamięci.</span><span class="sxs-lookup"><span data-stu-id="5e892-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e892-132">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5e892-132">Requirements</span></span>  

 <span data-ttu-id="5e892-133">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e892-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e892-134">**Nagłówek:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="5e892-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5e892-135">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5e892-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e892-136">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e892-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e892-137">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5e892-137">See also</span></span>

- [<span data-ttu-id="5e892-138">ICLRDataTarget2 — Interfejs</span><span class="sxs-lookup"><span data-stu-id="5e892-138">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="5e892-139">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="5e892-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
