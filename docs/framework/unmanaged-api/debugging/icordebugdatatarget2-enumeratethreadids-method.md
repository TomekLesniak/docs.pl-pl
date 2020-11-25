---
title: Metoda ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 31a839076b34901ae1a8f3b43021f64f77629fc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713850"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="5d83c-102">Metoda ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="5d83c-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>

<span data-ttu-id="5d83c-103">Zwraca listę aktywnych identyfikatorów wątków.</span><span class="sxs-lookup"><span data-stu-id="5d83c-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d83c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="5d83c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d83c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="5d83c-105">Parameters</span></span>  

 <span data-ttu-id="5d83c-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="5d83c-106">cThreadIDs</span></span>  
 <span data-ttu-id="5d83c-107">podczas Maksymalna liczba wątków, których identyfikatory można zwrócić.</span><span class="sxs-lookup"><span data-stu-id="5d83c-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="5d83c-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="5d83c-108">pcThreadIds</span></span>  
 <span data-ttu-id="5d83c-109">określoną Wskaźnik `ULONG32` wskazujący rzeczywistą liczbę identyfikatorów wątków zapisaną w `pThreadIds` tablicy.</span><span class="sxs-lookup"><span data-stu-id="5d83c-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="5d83c-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="5d83c-110">pThreadIDs</span></span>  
 <span data-ttu-id="5d83c-111">Tablica identyfikatorów wątków.</span><span class="sxs-lookup"><span data-stu-id="5d83c-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d83c-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5d83c-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d83c-113">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5d83c-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d83c-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="5d83c-114">Requirements</span></span>  

 <span data-ttu-id="5d83c-115">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md). **Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5d83c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d83c-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5d83c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d83c-117">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d83c-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d83c-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="5d83c-118">See also</span></span>

- [<span data-ttu-id="5d83c-119">Interfejs ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="5d83c-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="5d83c-120">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="5d83c-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
