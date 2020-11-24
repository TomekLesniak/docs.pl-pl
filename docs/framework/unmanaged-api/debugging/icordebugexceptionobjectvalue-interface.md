---
title: ICorDebugExceptionObjectValue — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
ms.openlocfilehash: 6a0c33799b2b2aaa48e3b18b7b4bb37643508bd4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678886"
---
# <a name="icordebugexceptionobjectvalue-interface"></a>ICorDebugExceptionObjectValue — Interfejs

Rozszerza interfejs "ICorDebugObjectValue", aby dostarczyć informacje o śledzeniu stosu z obiektu wyjątku zarządzanego.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[EnumerateExceptionCallStack, metoda](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|Pobiera moduł wyliczający w stosie wywołań osadzonym w obiekcie wyjątku.|  
  
## <a name="remarks"></a>Uwagi  

 Wywołanie powiedzie `QueryInterface` się dla obiektów zarządzanych, które pochodzą od <xref:System.Exception?displayProperty=nameWithType> .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
