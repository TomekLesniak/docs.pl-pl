---
title: ICorDebugManagedCallback2::ChangeConnection — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
ms.openlocfilehash: 4ba04b1a4815587b40d03819fdac795dcc7f2c4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697275"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a>ICorDebugManagedCallback2::ChangeConnection — Metoda

Powiadamia debuger o zmianie zestawu zadań skojarzonych z określonym połączeniem.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pProcess`  
 podczas Wskaźnik do obiektu "ICorDebugProcess", który reprezentuje proces zawierający połączenie, które uległo zmianie.  
  
 `dwConnectionId`  
 podczas Identyfikator zmienionego połączenia.  
  
## <a name="remarks"></a>Uwagi  

 `ChangeConnection`Wywołanie zwrotne zostanie wyzwolone w jednej z następujących sytuacji:  
  
- Gdy debuger dołącza do procesu, który zawiera połączenia. W takim przypadku środowisko uruchomieniowe generuje i wyśle zdarzenie [ICorDebugManagedCallback2::](icordebugmanagedcallback2-createconnection-method.md) CreateProcess oraz `ChangeConnection` zdarzenie dla każdego połączenia w procesie. `ChangeConnection`Dla każdego istniejącego połączenia generowane jest zdarzenie, niezależnie od tego, czy zestaw zadań tego połączenia został zmieniony od czasu jego utworzenia.  
  
- Gdy host wywołuje [ICLRDebugManager:: SetConnectionTasks —](../hosting/iclrdebugmanager-setconnectiontasks-method.md) w [interfejsie API hostingu](../hosting/index.md).  
  
 Debuger powinien skanować wszystkie wątki w procesie, aby pobrać nowe zmiany.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugManagedCallback2 — Interfejs](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback — Interfejs](icordebugmanagedcallback-interface.md)
