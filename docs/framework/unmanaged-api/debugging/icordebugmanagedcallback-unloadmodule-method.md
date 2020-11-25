---
title: ICorDebugManagedCallback::UnloadModule — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
ms.openlocfilehash: f24d49189ee81a80397b94ee4113c9514c083dbc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723990"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a>ICorDebugManagedCallback::UnloadModule — Metoda

Powiadamia debuger, że moduł środowiska uruchomieniowego języka wspólnego (DLL) został zwolniony.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pAppDomain`  
 podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji, która zawiera moduł.  
  
 `pModule`  
 podczas Wskaźnik do obiektu ICorDebugModule, który reprezentuje moduł.  
  
## <a name="remarks"></a>Uwagi  

 Modułu nie należy używać po tym wywołaniu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [LoadModule, metoda](icordebugmanagedcallback-loadmodule-method.md)
- [ICorDebugManagedCallback — Interfejs](icordebugmanagedcallback-interface.md)
