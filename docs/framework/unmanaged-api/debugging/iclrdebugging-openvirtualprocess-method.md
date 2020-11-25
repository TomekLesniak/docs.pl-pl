---
title: ICLRDebugging::OpenVirtualProcess — Metoda
ms.date: 03/30/2017
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
ms.openlocfilehash: 2edd7f628e17c8dc6cbcbb577d06269ba8c64cb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723546"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a>ICLRDebugging::OpenVirtualProcess — Metoda

Pobiera interfejs ICorDebugProcess, który odnosi się do modułu środowiska uruchomieniowego języka wspólnego (CLR) załadowanego w procesie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
## <a name="parameters"></a>Parametry  

 `moduleBaseAddress`  
 podczas Adres podstawowy modułu w procesie docelowym. COR_E_NOT_CLR będzie zwracana, jeśli określony moduł nie jest modułem CLR.  
  
 `pDataTarget`  
 podczas Abstrakcja elementu docelowego danych umożliwiająca zarządzanemu debugerowi sprawdzenie stanu procesu. Debuger musi implementować interfejs [ICorDebugDataTarget](icordebugdatatarget-interface.md) . Należy zaimplementować interfejs [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) , aby obsługiwał scenariusze, w których DEBUGOWANE środowisko CLR nie jest zainstalowane lokalnie na komputerze.  
  
 `pLibraryProvider`  
 podczas Interfejs wywołania zwrotnego dostawcy biblioteki, który umożliwia zlokalizowanie i załadowanie bibliotek debugowania specyficznych dla wersji na żądanie. Ten parametr jest wymagany tylko wtedy `ppProcess` , gdy lub `pFlags` nie jest `null` .  
  
 `pMaxDebuggerSupportedVersion`  
 podczas Największa wersja środowiska CLR, którą może debugować ten debuger. Należy określić wersje główne, pomocnicze i kompilacje od najnowszej wersji środowiska CLR obsługiwane przez ten debuger i ustawić numer poprawki na 65535 w celu uwzględnienia przyszłych wydań obsługi środowiska CLR w przyszłości.  
  
 `riidProcess`  
 podczas Identyfikator interfejsu ICorDebugProcess do pobrania. Obecnie Jedyne akceptowane wartości to IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 i IID_CORDEBUGPROCESS.  
  
 `ppProcess`  
 określoną Wskaźnik do interfejsu COM, który jest identyfikowany przez `riidProcess` .  
  
 `pVersion`  
 [in. out] Wersja środowiska CLR. Na wejściu ta wartość może być równa `null` . Może również wskazywać na strukturę [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) , w którym przypadku `wStructVersion` pole struktury musi być zainicjowane na 0 (zero).  
  
 W danych wyjściowych zwrócona `CLR_DEBUGGING_VERSION` Struktura zostanie wypełniona informacjami o wersji środowiska CLR.  
  
 `pdwFlags`  
 określoną Flagi informacyjne dotyczące określonego środowiska uruchomieniowego. Opis flag można znaleźć w temacie [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) .  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Metoda została ukończona pomyślnie.|  
|E_POINTER|`pDataTarget` to `null`.|  
|CORDBG_E_LIBRARY_PROVIDER_ERROR|Wywołanie zwrotne [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) zwraca błąd lub nie zapewnia prawidłowego dojścia.|  
|CORDBG_E_MISSING_DATA_TARGET_INTERFACE|`pDataTarget` Program nie implementuje wymaganych interfejsów obiektów docelowych danych dla tej wersji środowiska uruchomieniowego.|  
|CORDBG_E_NOT_CLR|Wskazany moduł nie jest modułem CLR. Ten wynik HRESULT jest również zwracany, gdy nie można wykryć modułu CLR, ponieważ pamięć została uszkodzona, moduł jest niedostępny lub wersja środowiska CLR jest nowsza niż wersja podkładki.|  
|CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL|Ta wersja środowiska uruchomieniowego nie obsługuje tego modelu debugowania. Obecnie model debugowania nie jest obsługiwany przez wersje środowiska CLR przed .NET Framework 4. `pwszVersion`Parametr wyjściowy jest nadal ustawiany na poprawną wartość po wystąpieniu tego błędu.|  
|CORDBG_E_UNSUPPORTED_FORWARD_COMPAT|Wersja środowiska CLR jest nowsza niż wersja tego debugera do obsługi. `pwszVersion`Parametr wyjściowy jest nadal ustawiany na poprawną wartość po wystąpieniu tego błędu.|  
|E_NO_INTERFACE|`riidProcess`Interfejs jest niedostępny.|  
|CORDBG_E_UNSUPPORTED_VERSION_STRUCT|`CLR_DEBUGGING_VERSION`Struktura nie ma rozpoznawanej wartości dla `wStructVersion` . Jedyną akceptowaną wartością w tym momencie jest 0.|  
  
## <a name="exceptions"></a>Wyjątki  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
