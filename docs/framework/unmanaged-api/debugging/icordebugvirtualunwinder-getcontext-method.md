---
title: 'ICorDebugVirtualUnwinder:: GetContext — Metoda'
ms.date: 03/30/2017
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
ms.openlocfilehash: a5a1afa47e52eff7c930698a3354a03d8c62259f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679458"
---
# <a name="icordebugvirtualunwindergetcontext-method"></a><span data-ttu-id="a6a6e-102">ICorDebugVirtualUnwinder:: GetContext — Metoda</span><span class="sxs-lookup"><span data-stu-id="a6a6e-102">ICorDebugVirtualUnwinder::GetContext Method</span></span>

<span data-ttu-id="a6a6e-103">Pobiera bieżący kontekst tego elementu unwiatrer.</span><span class="sxs-lookup"><span data-stu-id="a6a6e-103">Gets the current context of this unwinder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6a6e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="a6a6e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6a6e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="a6a6e-105">Parameters</span></span>  

 `contextFlags`  
 <span data-ttu-id="a6a6e-106">podczas Flagi określające, które części kontekstu mają być zwracane (zdefiniowane w WinNT. h).</span><span class="sxs-lookup"><span data-stu-id="a6a6e-106">[in] Flags that specify which parts of the context to return (defined in WinNT.h).</span></span>  
  
 `cbContextBuf`  
 <span data-ttu-id="a6a6e-107">podczas Liczba bajtów w `contextBuf` .</span><span class="sxs-lookup"><span data-stu-id="a6a6e-107">[in] The number of bytes in `contextBuf`.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="a6a6e-108">określoną Wskaźnik do liczby bajtów, które są w rzeczywistości zapisywane `contextBuf` .</span><span class="sxs-lookup"><span data-stu-id="a6a6e-108">[out] A pointer to the number of bytes actually written to `contextBuf`.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="a6a6e-109">określoną Tablica bajtów, która zawiera bieżący kontekst tego elementu unwiatrer.</span><span class="sxs-lookup"><span data-stu-id="a6a6e-109">[out] A byte array that contains the current context of this unwinder.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6a6e-110">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="a6a6e-110">Return Value</span></span>  

 <span data-ttu-id="a6a6e-111">Wszystkie niepowodzenie wartości HRESULT otrzymanej przez mscordbi jest uznawane za krytyczne i spowoduje zwrócenie interfejsów API ICorDebug `CORDBG_E_DATA_TARGET_ERROR` .</span><span class="sxs-lookup"><span data-stu-id="a6a6e-111">Any failing HRESULT value received by mscordbi is considered fatal and will cause ICorDebug APIs to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6a6e-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a6a6e-112">Remarks</span></span>  

 <span data-ttu-id="a6a6e-113">Ustawiasz początkową wartość `contextBuf` argumentu dla buforu kontekstu zwracanego przez wywołanie metody [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a6a6e-113">You set the initial value of the `contextBuf` argument to the context buffer returned by calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6a6e-114">Ta metoda jest dostępna tylko z .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a6a6e-114">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="a6a6e-115">Ponieważ rozwinięcia może przywrócić tylko podzestaw rejestrów, takich jak tylko rejestry nielotne, kontekst może nie być dokładnie zgodny z stanem rejestru w chwili rzeczywistego wywołania metody.</span><span class="sxs-lookup"><span data-stu-id="a6a6e-115">Because unwinding may only restore a subset of the registers, such as the non-volatile registers only, the context may not exactly match the register state at the time of the actual method call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6a6e-116">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a6a6e-116">Requirements</span></span>  

 <span data-ttu-id="a6a6e-117">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6a6e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6a6e-118">**Nagłówek:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="a6a6e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6a6e-119">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a6a6e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6a6e-120">**.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6a6e-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6a6e-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a6a6e-121">See also</span></span>

- [<span data-ttu-id="a6a6e-122">ICorDebugMemoryBuffer, interfejs</span><span class="sxs-lookup"><span data-stu-id="a6a6e-122">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="a6a6e-123">Debugowanie — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="a6a6e-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
