---
title: ICorDebugManagedCallback2::FunctionRemapOpportunity — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
ms.openlocfilehash: 50fabec08a63d348b0a1934f029582ae1446519e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729060"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a>ICorDebugManagedCallback2::FunctionRemapOpportunity — Metoda

Powiadamia debuger, że wykonanie kodu osiągnęło punkt sekwencji w starszej wersji edytowanej funkcji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pAppDomain`  
 podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji zawierającą edytowaną funkcję.  
  
 `pThread`  
 podczas Wskaźnik do obiektu ICorDebugThread, który reprezentuje wątek, w którym napotkano punkt przerwania mapowania.  
  
 `pOldFunction`  
 podczas Wskaźnik do obiektu ICorDebugFunction, który reprezentuje wersję funkcji, która jest aktualnie uruchomiona w wątku.  
  
 `pNewFunction`  
 podczas Wskaźnik do obiektu ICorDebugFunction, który reprezentuje najnowszą wersję funkcji.  
  
 `oldILOffset`  
 podczas Przesunięcie języka pośredniego firmy Microsoft (MSIL) wskaźnika instrukcji w starej wersji funkcji.  
  
## <a name="remarks"></a>Uwagi  

 To wywołanie zwrotne daje debugerowi możliwość ponownego mapowania wskaźnika instrukcji do odpowiedniego miejsca w nowej wersji określonej funkcji przez wywołanie metody [ICorDebugILFrame2:: RemapFunction](icordebugilframe2-remapfunction-method.md) . Jeśli debuger nie wywołuje `RemapFunction` przed wywołaniem metody [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , środowisko uruchomieniowe będzie kontynuowało wykonywanie starego kodu i spowoduje uruchomienie innego `FunctionRemapOpportunity` wywołania zwrotnego w następnym punkcie sekwencji.  
  
 To wywołanie zwrotne zostanie wywołane dla każdej ramki, która wykonuje starszą wersję danej funkcji, dopóki debuger nie zwróci S_OK.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugManagedCallback2 — Interfejs](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback — Interfejs](icordebugmanagedcallback-interface.md)
