---
title: ICorDebugManagedCallback::LoadModule — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
ms.openlocfilehash: 698a5cb88884febc4dfb3b916c00df20c1a77819
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679653"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a>ICorDebugManagedCallback::LoadModule — Metoda

Powiadamia debuger o pomyślnym załadowaniu modułu środowiska uruchomieniowego języka wspólnego (CLR).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pAppDomain`  
 podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji, do której moduł został załadowany.  
  
 `pModule`  
 podczas Wskaźnik do obiektu ICorDebugModule, który reprezentuje moduł CLR.  
  
## <a name="remarks"></a>Uwagi  

 `LoadModule`Wywołanie zwrotne zapewnia odpowiedni czas na sprawdzenie metadanych modułu, ustawienie flag kompilatora just-in-Time (JIT) lub włączenie lub wyłączenie wywołania zwrotnego ładowania klasy dla modułu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [UnloadModule, metoda](icordebugmanagedcallback-unloadmodule-method.md)
- [ICorDebugManagedCallback — Interfejs](icordebugmanagedcallback-interface.md)
