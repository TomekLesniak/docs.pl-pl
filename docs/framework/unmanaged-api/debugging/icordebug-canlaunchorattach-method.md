---
title: ICorDebug::CanLaunchOrAttach — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
ms.openlocfilehash: 195c7e1e7c61fd6ac8a21226b52e3782d2f7e421
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723496"
---
# <a name="icordebugcanlaunchorattach-method"></a>ICorDebug::CanLaunchOrAttach — Metoda

Zwraca wartość HRESULT wskazującą, czy uruchomienie nowego procesu lub dołączenie do określonego istniejącego procesu jest możliwe w kontekście bieżącego komputera i konfiguracji środowiska uruchomieniowego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `dwProcessId`  
 podczas Identyfikator istniejącego procesu.  
  
 `win32DebuggingEnabled`  
 podczas Zastąp `true` , jeśli planujesz uruchamianie z włączonym debugowaniem Win32 lub dołączanie z włączonym debugowaniem Win32; w przeciwnym razie Przekaż `false` .  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK, jeśli usługa debugowania określi, że uruchomienie nowego procesu lub dołączenie do danego procesu jest możliwe, z uwzględnieniem informacji o bieżącym komputerze i konfiguracji środowiska uruchomieniowego. Możliwe wartości HRESULT to:  
  
- S_OK  
  
- CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
- CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
- CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>Uwagi  

 Ta metoda ma charakter czysty informacyjny. Interfejs nie zatrzymuje uruchamiania lub dołączania do procesu, niezależnie od wartości zwracanej przez `CanLaunchOrAttach` .  
  
 Jeśli planujesz uruchamianie z włączonym debugowaniem Win32 lub Dołącz z włączonym debugowaniem Win32, Przekaż `true` `win32DebuggingEnabled` . Wartość HRESULT zwracaną przez `CanLaunchOrAttach` może się różnić w przypadku użycia tej opcji.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebug — Interfejs](icordebug-interface.md)
