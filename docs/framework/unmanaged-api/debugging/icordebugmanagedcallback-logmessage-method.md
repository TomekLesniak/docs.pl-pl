---
title: ICorDebugManagedCallback::LogMessage — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
ms.openlocfilehash: 92b2a7f7f1dd98f0d847119a6431e3816c16d5da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679575"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a>ICorDebugManagedCallback::LogMessage — Metoda

Powiadamia debuger, że wątek zarządzany środowiska uruchomieniowego języka wspólnego (CLR) wezwał metodę w <xref:System.Diagnostics.EventLog> klasie, aby zarejestrować zdarzenie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pAppDomain`  
 podczas Wskaźnik do obiektu ICorDebugAppDomain, który reprezentuje domenę aplikacji zawierającą zarządzany wątek, który zarejestrował zdarzenie.  
  
 `pThread`  
 podczas Wskaźnik do obiektu ICorDebugThread, który reprezentuje wątek zarządzany.  
  
 `lLevel`  
 podczas Wartość wyliczenia [LoggingLevelEnum —](logginglevelenum-enumeration.md) , która wskazuje poziom ważności komunikatu opisowego, który został zapisany w dzienniku zdarzeń.  
  
 `pLogSwitchName`  
 podczas Wskaźnik do nazwy przełącznika śledzenia.  
  
 `pMessage`  
 podczas Wskaźnik do wiadomości, która została zapisywana w dzienniku zdarzeń.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugManagedCallback — Interfejs](icordebugmanagedcallback-interface.md)
