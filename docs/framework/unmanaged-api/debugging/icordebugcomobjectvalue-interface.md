---
title: ICorDebugComObjectValue — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
ms.openlocfilehash: 40df1416e68c86efe6d404119cb37277fe21ac56
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677547"
---
# <a name="icordebugcomobjectvalue-interface"></a>ICorDebugComObjectValue — Interfejs

Dostarcza metody do pobierania informacji skojarzonych z otoką w czasie wykonywania (otoka).  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetCachedInterfacePointers, metoda](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|Pobiera pierwotne wskaźniki interfejsu w pamięci podręcznej w bieżącej otoki RCW.|  
|[GetCachedInterfaceTypes, metoda](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|Dostarcza moduł wyliczający dla typów interfejsów, do których jest uwzględniany bieżący obiekt lub do których służy.|  
  
## <a name="remarks"></a>Uwagi  

 Aby sprawdzić, czy wystąpienie interfejsu "ICorDebugValue" reprezentuje otokę RCW, debuger wywołuje polecenie `QueryInterface` "ICorDebugValue" z `IID_ICorDebugComObjectValue` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
