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
# <a name="icordebugvariablesymbolgetvalue-method"></a>ICorDebugVariableSymbol:: GetValue — Metoda

Pobiera wartość zmiennej jako tablicę bajtów.  
  
## <a name="syntax"></a>Składnia  
  
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
  
## <a name="parameters"></a>Parametry  

 `offset`  
 podczas Przesunięcie początkowe w zmiennej, z której ma zostać odczytana wartość. Ten parametr jest używany podczas odczytywania pól elementu członkowskiego w obiekcie.  
  
 `cbContext`  
 podczas Rozmiar w bajtach `context` argumentu.  
  
 `context`  
 podczas Kontekst wątku używany do odczytywania wartości.  
  
 `cbValue`  
 podczas Rozmiar w bajtach `pValue` buforu.  
  
 `pcbValue`  
 określoną Liczba bajtów rzeczywiście zapisywana w `pValue` buforze.  
  
 `pValue`  
 określoną Tablica bajtów, która zawiera wartość zmiennej.  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ta metoda jest dostępna tylko z .NET Native.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugVariableSymbol, interfejs](icordebugvariablesymbol-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
