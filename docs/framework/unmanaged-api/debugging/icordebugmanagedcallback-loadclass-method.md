---
title: ICorDebugManagedCallback::LoadClass — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
ms.openlocfilehash: 6f1672d40cd495d3ec099abc703639cf52460703
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679666"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a>ICorDebugManagedCallback::LoadClass — Metoda

Powiadamia debuger o załadowaniu klasy.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pAppDomain`  
 podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji, do której Klasa została załadowana.  
  
 `c`  
 podczas Wskaźnik do obiektu ICorDebugClass, który reprezentuje klasę.  
  
## <a name="remarks"></a>Uwagi  

 To wywołanie zwrotne występuje tylko wtedy, gdy dla modułu zawierającego klasę włączono funkcję ładowania klasy. Ładowanie klasy jest zawsze włączone dla modułów dynamicznych.  
  
 `LoadClass`Wywołanie zwrotne zapewnia odpowiedni czas na powiązanie punktów przerwania z nowo wygenerowanymi klasami w modułach dynamicznych.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [UnloadClass, metoda](icordebugmanagedcallback-unloadclass-method.md)
- [ICorDebugManagedCallback — Interfejs](icordebugmanagedcallback-interface.md)
