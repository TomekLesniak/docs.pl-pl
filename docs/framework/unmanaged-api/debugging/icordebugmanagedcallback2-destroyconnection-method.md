---
title: ICorDebugManagedCallback2::DestroyConnection — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.DestroyConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type:
- apiref
ms.openlocfilehash: d725cbe89e0631630affb6b0540a7d5f57ab6b89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720116"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a>ICorDebugManagedCallback2::DestroyConnection — Metoda

Powiadamia debuger o przerwaniu określonego połączenia.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pProcess`  
 podczas Wskaźnik do obiektu ICorDebugProcess, który reprezentuje proces zawierający zniszczone połączenie.  
  
 `dwConnectionId`  
 podczas Identyfikator zerwanego połączenia.  
  
## <a name="remarks"></a>Uwagi  

 `DestroyConnection`Wywołanie zwrotne zostanie wyzwolone, gdy host wywoła [ICLRDebugManager:: EndConnection —](../hosting/iclrdebugmanager-endconnection-method.md) w [interfejsie API hostingu](../hosting/index.md).  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugManagedCallback2 — Interfejs](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback — Interfejs](icordebugmanagedcallback-interface.md)
