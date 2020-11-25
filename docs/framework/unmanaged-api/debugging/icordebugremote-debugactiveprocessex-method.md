---
title: ICorDebugRemote::DebugActiveProcessEx — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
ms.openlocfilehash: c9847fd6122aa32c95aecd5643a62a6775ae38d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712121"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a>ICorDebugRemote::DebugActiveProcessEx — Metoda

Uruchamia proces na maszynie zdalnej pod debugerem.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pRemoteTarget`  
 podczas Wskaźnik do [interfejsu ICorDebugRemoteTarget](icordebugremotetarget-interface.md). Ten parametr służy do określania komputera, na którym jest uruchomiony proces.  
  
 `id`  
 podczas Identyfikator procesu, do którego ma zostać dołączony debuger.  
  
 `win32Attach`  
 [w] `true` Jeśli debuger powinien działać jako debuger Win32 dla procesu i wysyłać niezarządzane wywołania zwrotne; w przeciwnym razie `false` .  
  
 `ppProcess`  
 określoną Wskaźnik do adresu obiektu "ICorDebugProcess", który reprezentuje proces, do którego został podłączony debuger.  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK  
 Pomyślnie dołączono do procesu na komputerze zdalnym.  
  
 E_FAIL (lub inne kody powrotne E_)  
 Nie można dołączyć do procesu na komputerze zdalnym.  
  
## <a name="remarks"></a>Uwagi  

 Debugowanie w trybie mieszanym nie jest obsługiwane w programie Silverlight.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugRemote — Interfejs](icordebugremote-interface.md)
- [ICorDebug — Interfejs](icordebug-interface.md)

- [Debugowanie — Interfejsy](debugging-interfaces.md)
