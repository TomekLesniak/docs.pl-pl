---
title: ICorDebugProcess::GetThreadContext — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
ms.openlocfilehash: 3be689e5c1474bcbfbca72a14a298762dc2e7a90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724549"
---
# <a name="icordebugprocessgetthreadcontext-method"></a>ICorDebugProcess::GetThreadContext — Metoda

Pobiera kontekst dla danego wątku w tym procesie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a>Parametry  

 `threadID`  
 podczas Identyfikator wątku, dla którego ma zostać pobrany kontekst.  
  
 `contextSize`  
 podczas Rozmiar `context` tablicy.  
  
 `context`  
 [in. out] Tablica bajtów opisująca kontekst wątku.  
  
 Kontekst określa architekturę procesora, w którym wykonywany jest wątek.  
  
## <a name="remarks"></a>Uwagi  

 Debuger powinien wywołać tę metodę zamiast `GetThreadContext` metody Win32, ponieważ wątek może być w stanie "przejęte", w którym jego kontekst został tymczasowo zmieniony. Ta metoda powinna być używana tylko wtedy, gdy wątek znajduje się w kodzie natywnym. Użyj [ICorDebugRegisterSet](icordebugregisterset-interface.md) dla wątków w kodzie zarządzanym.  
  
 Zwrócone dane są strukturą kontekstu dla bieżącej platformy. Podobnie jak w przypadku `GetThreadContext` metody Win32, obiekt wywołujący powinien inicjować `context` parametr przed wywołaniem tej metody.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
