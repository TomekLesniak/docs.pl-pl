---
title: ICorDebugManagedCallback::UnloadAssembly — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
ms.openlocfilehash: e89b425afb63de8ef496fe545873ce33e5ff828c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724016"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a>ICorDebugManagedCallback::UnloadAssembly — Metoda

Powiadamia debuger, że zestaw środowiska uruchomieniowego języka wspólnego został zwolniony.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pAppDomain`  
 podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji, która zawiera zestaw.  
  
 `pAssembly`  
 podczas Wskaźnik do obiektu ICorDebugAssembly, który reprezentuje zestaw.  
  
## <a name="remarks"></a>Uwagi  

 Zestawu nie należy używać po tym wywołaniu zwrotnym.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [LoadAssembly, metoda](icordebugmanagedcallback-loadassembly-method.md)
- [ICorDebugManagedCallback — Interfejs](icordebugmanagedcallback-interface.md)
