---
title: 'ICorDebugVariableSymbol:: GetSlotIndex, Metoda'
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: fc42517cb95dfc14c472b5bb9111ebd70639cee7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725992"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="4678c-102">ICorDebugVariableSymbol:: GetSlotIndex, Metoda</span><span class="sxs-lookup"><span data-stu-id="4678c-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>

<span data-ttu-id="4678c-103">Pobiera indeks gniazda zarządzanego zmiennej lokalnej.</span><span class="sxs-lookup"><span data-stu-id="4678c-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4678c-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4678c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4678c-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="4678c-105">Parameters</span></span>  

 `pSlotIndex`  
 <span data-ttu-id="4678c-106">określoną Wskaźnik do indeksu gniazda zmiennej lokalnej.</span><span class="sxs-lookup"><span data-stu-id="4678c-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4678c-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="4678c-107">Return Value</span></span>  

 <span data-ttu-id="4678c-108">`S_OK` w przypadku powodzenia.</span><span class="sxs-lookup"><span data-stu-id="4678c-108">`S_OK` if successful.</span></span> <span data-ttu-id="4678c-109">`E_FAIL` Jeśli zmienna jest argumentem funkcji.</span><span class="sxs-lookup"><span data-stu-id="4678c-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4678c-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4678c-110">Remarks</span></span>  

 <span data-ttu-id="4678c-111">Do pobrania informacji o metadanych zmiennej można użyć indeksu gniazda zarządzanego zmiennej lokalnej.</span><span class="sxs-lookup"><span data-stu-id="4678c-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4678c-112">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4678c-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4678c-113">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4678c-113">Requirements</span></span>  

 <span data-ttu-id="4678c-114">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4678c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4678c-115">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="4678c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4678c-116">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4678c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4678c-117">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4678c-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4678c-118">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4678c-118">See also</span></span>

- [<span data-ttu-id="4678c-119">ICorDebugVariableSymbol, interfejs</span><span class="sxs-lookup"><span data-stu-id="4678c-119">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="4678c-120">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="4678c-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
