---
title: ICorDebugObjectValue, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: 2a5a618491bf2c624669728d97a690cca315bff8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724679"
---
# <a name="icordebugobjectvalue-interface"></a>ICorDebugObjectValue, interfejs

Podklasa elementu "ICorDebugValue" reprezentująca wartość, która zawiera obiekt.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetClass, metoda](icordebugobjectvalue-getclass-method.md)|Pobiera wskaźnik interfejsu do środowiska uruchomieniowego języka wspólnego (CLR) <xref:System.Type> obiektu, do którego `ICorDebugObjectValue` odwołuje się to odwołanie.|  
|[GetContext — Metoda](icordebugobjectvalue-getcontext-method.md)|Nie zaimplementowano.|  
|[GetFieldValue, metoda](icordebugobjectvalue-getfieldvalue-method.md)|Pobiera wskaźnik interfejsu do elementu [ICorDebugValue](icordebugvalue-interface.md) , który reprezentuje wartość określonego pola określonej klasy.|  
|[GetManagedCopy, metoda](icordebugobjectvalue-getmanagedcopy-method.md)|Nieaktualne. Nie wywołuj tej metody.|  
|[GetVirtualMethod, metoda](icordebugobjectvalue-getvirtualmethod-method.md)|Nie zaimplementowano.|  
|[IsValueClass, metoda](icordebugobjectvalue-isvalueclass-method.md)|Pobiera wartość wskazującą, czy obiekt, do którego odwołuje się to `ICorDebugObjectValue` Typ wartości.|  
|[SetFromManagedCopy, metoda](icordebugobjectvalue-setfrommanagedcopy-method.md)|Nieaktualne. Nie wywołuj tej metody.|  
  
## <a name="remarks"></a>Uwagi  

 `ICorDebugObjectValue`Pozostanie on ważny do momentu, gdy debugowany proces jest kontynuowany.  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
