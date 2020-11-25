---
title: ICorDebug::DebugActiveProcess — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 1713623fa575bea6df649106b37212f7aeaee6db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723470"
---
# <a name="icordebugdebugactiveprocess-method"></a>ICorDebug::DebugActiveProcess — Metoda

Dołącza debuger do istniejącego procesu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `id`  
 podczas Identyfikator procesu, do którego ma zostać dołączony debuger.  
  
 `win32Attach`  
 podczas Wartość logiczna, która jest ustawiona na, `true` Jeśli debuger powinien zachowywać się jako debuger Win32 dla procesu i wysyłał niezarządzane wywołania zwrotne; w przeciwnym razie `false` .  
  
 `ppProcess`  
 określoną Wskaźnik do adresu obiektu "ICorDebugProcess", który reprezentuje proces, do którego został podłączony debuger.  
  
## <a name="remarks"></a>Uwagi  

 Debugowanie międzyoperacyjności nie jest obsługiwane na platformach Win9x i innych niż x86, na przykład na platformach opartych na architekturze IA-64 i AMD64.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebug — Interfejs](icordebug-interface.md)
