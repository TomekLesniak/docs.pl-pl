---
title: 'ICorDebugExceptionDebugEvent:: GetStackPointer, Metoda'
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 46906e7d3ce7f257eb776e50dc6097946eb77d1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697405"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a>ICorDebugExceptionDebugEvent:: GetStackPointer, Metoda

Pobiera wskaźnik stosu dla tego zdarzenia debugowania wyjątku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pStackPointer`  
 określoną Wskaźnik do adresu wskaźnika stosu dla tego zdarzenia debugowania wyjątku. Zobacz sekcję Spostrzeżenia, aby uzyskać więcej informacji.  
  
## <a name="remarks"></a>Uwagi  

 Znaczenie tego wskaźnika stosu zależy od typu zdarzenia, jak pokazano w poniższej tabeli.  
  
|Typ zdarzenia|Znaczenie `pStackPointer` wartości|  
|----------------|--------------------------------------|  
|[MANAGED_EXCEPTION_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|Wskaźnik stosu dla ramki, która wywołała wyjątek.|  
|[MANAGED_EXCEPTION_USER_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|Wskaźnik stosu dla ramki kodu użytkownika znajdującej się najbliżej punktu zgłoszonego wyjątku.|  
|[MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](cordebugrecordformat-enumeration.md)|Wskaźnik stosu dla ramki, która zawiera procedurę obsługi catch.|  
|[MANAGED_EXCEPTION_UNHANDLED](cordebugrecordformat-enumeration.md)|`pStackPointer` ma **wartość null**.|  
  
> [!NOTE]
> Ta metoda jest dostępna tylko z .NET Native.  
  
 Typ zdarzenia jest dostępny w metodzie [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejs ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
