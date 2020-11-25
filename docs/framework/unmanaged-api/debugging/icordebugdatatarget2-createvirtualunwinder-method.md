---
title: Metoda ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: 0967b1cda86eab35015279edeed9a6b9852036b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713941"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="46c0f-102">Metoda ICorDebugDataTarget2::CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="46c0f-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>

<span data-ttu-id="46c0f-103">Tworzy nowy wątek unwiatrer, który zaczyna odwracać od kontekstu początkowego (co nie musi być elementem liścia wątku).</span><span class="sxs-lookup"><span data-stu-id="46c0f-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46c0f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="46c0f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a><span data-ttu-id="46c0f-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="46c0f-105">Parameters</span></span>  

 <span data-ttu-id="46c0f-106">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="46c0f-106">nativeThreadID</span></span>  
 <span data-ttu-id="46c0f-107">podczas Identyfikator wątku natywnego wątku, którego stos ma być rozłożony.</span><span class="sxs-lookup"><span data-stu-id="46c0f-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="46c0f-108">contextFlags</span><span class="sxs-lookup"><span data-stu-id="46c0f-108">contextFlags</span></span>  
 <span data-ttu-id="46c0f-109">podczas Flagi określające, w których częściach kontekstu są zdefiniowane `initialContext` .</span><span class="sxs-lookup"><span data-stu-id="46c0f-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="46c0f-110">cbContext</span><span class="sxs-lookup"><span data-stu-id="46c0f-110">cbContext</span></span>  
 <span data-ttu-id="46c0f-111">podczas Rozmiar `initialContext` .</span><span class="sxs-lookup"><span data-stu-id="46c0f-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="46c0f-112">initialContext</span><span class="sxs-lookup"><span data-stu-id="46c0f-112">initialContext</span></span>  
 <span data-ttu-id="46c0f-113">podczas Dane w kontekście.</span><span class="sxs-lookup"><span data-stu-id="46c0f-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="46c0f-114">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="46c0f-114">ppUnwinder</span></span>  
 <span data-ttu-id="46c0f-115">określoną Wskaźnik do adresu obiektu interfejsu ICorDebugVirtualUnwinder.</span><span class="sxs-lookup"><span data-stu-id="46c0f-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46c0f-116">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="46c0f-116">Return Value</span></span>  

 <span data-ttu-id="46c0f-117">`S_OK` w przypadku powodzenia.</span><span class="sxs-lookup"><span data-stu-id="46c0f-117">`S_OK` if successful.</span></span> <span data-ttu-id="46c0f-118">Wszystkie inne `HRESULT` wskazuje na błąd.</span><span class="sxs-lookup"><span data-stu-id="46c0f-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="46c0f-119">Wszystkie błędy `HRESULT` odebrane przez mscordbi są uznawane za krytyczne i powodują zwrócenie metod [ICorDebug](icordebug-interface.md) `CORDBG_E_DATA_TARGET_ERROR` .</span><span class="sxs-lookup"><span data-stu-id="46c0f-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46c0f-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="46c0f-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="46c0f-121">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="46c0f-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46c0f-122">Wymagania</span><span class="sxs-lookup"><span data-stu-id="46c0f-122">Requirements</span></span>  

 <span data-ttu-id="46c0f-123">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46c0f-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46c0f-124">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="46c0f-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46c0f-125">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="46c0f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46c0f-126">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46c0f-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c0f-127">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="46c0f-127">See also</span></span>

- [<span data-ttu-id="46c0f-128">Interfejs ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="46c0f-128">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="46c0f-129">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="46c0f-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
