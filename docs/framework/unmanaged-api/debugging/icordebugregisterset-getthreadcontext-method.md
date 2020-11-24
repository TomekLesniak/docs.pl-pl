---
title: ICorDebugRegisterSet::GetThreadContext — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
ms.openlocfilehash: a7d78daf74d3cc01c2313f092bce53950dbd7bfb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681226"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a>ICorDebugRegisterSet::GetThreadContext — Metoda

Pobiera kontekst bieżącego wątku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `contextSize`  
 podczas Rozmiar tablicy w bajtach `context` .  
  
 `context`  
 [in. out] Tablica bajtów, która składa się ze `CONTEXT` struktury Win32 dla bieżącej platformy.  
  
## <a name="remarks"></a>Uwagi  

 Debuger powinien wywołać tę funkcję zamiast `GetThreadContext` funkcji Win32, ponieważ wątek może być w stanie "przejęte", gdzie jego kontekst został tymczasowo zmieniony. Zwrócone dane są `CONTEXT` strukturą Win32 dla bieżącej platformy.  
  
 W przypadku ramek spoza liścia klienci powinni sprawdzić, które rejestry są prawidłowe za pomocą [ICorDebugRegisterSet:: GetRegistersAvailable —](icordebugregisterset-getregistersavailable-method.md).  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugRegisterSet — Interfejs](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 — Interfejs](icordebugregisterset2-interface.md)
