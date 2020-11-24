---
title: ICorDebugThread2, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
ms.openlocfilehash: fd4ad536d7d3df2b8f91f206459122cf083c8b9c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691139"
---
# <a name="icordebugthread2-interface"></a>ICorDebugThread2, interfejs

Służy jako logiczne rozszerzenie interfejsu ICorDebugThread.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetActiveFunctions, metoda](icordebugthread2-getactivefunctions-method.md)|Pobiera tablicę wystąpień COR_ACTIVE_FUNCTION zawierających dane dotyczące aktywnych funkcji w ramkach wątku.|  
|[GetConnectionID, metoda](icordebugthread2-getconnectionid-method.md)|Pobiera identyfikator połączenia dla tego elementu `ICorDebugThread2` .|  
|[GetTaskID, metoda](icordebugthread2-gettaskid-method.md)|Pobiera identyfikator zadania dla tego elementu `ICorDebugThread2` .|  
|[GetVolatileOSThreadID, metoda](icordebugthread2-getvolatileosthreadid-method.md)|Pobiera identyfikator wątku systemu operacyjnego `ICorDebugThread2` .|  
|[InterceptCurrentException, metoda](icordebugthread2-interceptcurrentexception-method.md)|Umożliwia debugerowi przechwycenie bieżącego wyjątku w wątku.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
