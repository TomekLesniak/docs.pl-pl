---
title: 'ICorDebugVariableSymbol:: GetValue — Metoda'
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: 0a57b1a31e1ef4b0db317012b25bc65ecbbaf011
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725966"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="040e4-102">ICorDebugVariableSymbol:: GetValue — Metoda</span><span class="sxs-lookup"><span data-stu-id="040e4-102">ICorDebugVariableSymbol::GetValue Method</span></span>

<span data-ttu-id="040e4-103">Pobiera wartość zmiennej jako tablicę bajtów.</span><span class="sxs-lookup"><span data-stu-id="040e4-103">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="040e4-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="040e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="040e4-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="040e4-105">Parameters</span></span>  

 `offset`  
 <span data-ttu-id="040e4-106">podczas Przesunięcie początkowe w zmiennej, z której ma zostać odczytana wartość.</span><span class="sxs-lookup"><span data-stu-id="040e4-106">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="040e4-107">Ten parametr jest używany podczas odczytywania pól elementu członkowskiego w obiekcie.</span><span class="sxs-lookup"><span data-stu-id="040e4-107">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="040e4-108">podczas Rozmiar w bajtach `context` argumentu.</span><span class="sxs-lookup"><span data-stu-id="040e4-108">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="040e4-109">podczas Kontekst wątku używany do odczytywania wartości.</span><span class="sxs-lookup"><span data-stu-id="040e4-109">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="040e4-110">podczas Rozmiar w bajtach `pValue` buforu.</span><span class="sxs-lookup"><span data-stu-id="040e4-110">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="040e4-111">określoną Liczba bajtów rzeczywiście zapisywana w `pValue` buforze.</span><span class="sxs-lookup"><span data-stu-id="040e4-111">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="040e4-112">określoną Tablica bajtów, która zawiera wartość zmiennej.</span><span class="sxs-lookup"><span data-stu-id="040e4-112">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="040e4-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="040e4-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="040e4-114">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="040e4-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="040e4-115">Wymagania</span><span class="sxs-lookup"><span data-stu-id="040e4-115">Requirements</span></span>  

 <span data-ttu-id="040e4-116">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="040e4-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="040e4-117">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="040e4-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="040e4-118">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="040e4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="040e4-119">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="040e4-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="040e4-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="040e4-120">See also</span></span>

- [<span data-ttu-id="040e4-121">ICorDebugVariableSymbol, interfejs</span><span class="sxs-lookup"><span data-stu-id="040e4-121">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="040e4-122">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="040e4-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
