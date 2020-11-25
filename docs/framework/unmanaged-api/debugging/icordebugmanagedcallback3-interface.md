---
title: ICorDebugManagedCallback3 — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3
helpviewer_keywords:
- ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type:
- apiref
ms.openlocfilehash: e04f5be6d2612b26bf7d71807753d170e6a5a7a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723301"
---
# <a name="icordebugmanagedcallback3-interface"></a>ICorDebugManagedCallback3 — Interfejs

Dostarcza metodę wywołania zwrotnego, która wskazuje, że zgłoszono powiadomienie włączenia niestandardowego debugera.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[CustomNotification, metoda](icordebugmanagedcallback3-customnotification-method.md)|Wskazuje, że zostało zgłoszone włączone powiadomienie debugera niestandardowego.|  
  
## <a name="remarks"></a>Uwagi  

 Ten interfejs jest logicznym rozszerzeniem interfejsów [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) i [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugManagedCallback — Interfejs](icordebugmanagedcallback-interface.md)
- [ICorDebugManagedCallback2 — Interfejs](icordebugmanagedcallback2-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
