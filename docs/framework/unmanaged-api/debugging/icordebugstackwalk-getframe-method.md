---
title: ICorDebugStackWalk::GetFrame — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
ms.openlocfilehash: 452635764794e01858baab10464a03c966a55271
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711941"
---
# <a name="icordebugstackwalkgetframe-method"></a>ICorDebugStackWalk::GetFrame — Metoda

Pobiera bieżącą ramkę w obiekcie [ICorDebugStackWalk](icordebugstackwalk-interface.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a>Parametry  

 `pFrame`  
 podczas Wskaźnik do adresu utworzonego obiektu Frame, który reprezentuje bieżącą ramkę w stosie.  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Środowisko uruchomieniowe pomyślnie zwróciło bieżącą ramkę.|  
|E_FAIL|Bieżąca ramka nie została zwrócona.|  
|S_FALSE|Bieżąca ramka jest natywną ramką stosu.|  
|E_INVALIDARG|`pFrame` ma wartość null.|  
|CORDBG_E_PAST_END_OF_STACK|Wskaźnik ramki znajduje się już na końcu stosu; w związku z tym nie można uzyskać dostępu do dodatkowych ramek.|  
  
## <a name="exceptions"></a>Wyjątki  
  
## <a name="remarks"></a>Uwagi  

 `ICorDebugStackWalk` zwraca tylko rzeczywiste ramki stosu. Użyj metody [ICorDebugThread3:: GetActiveInternalFrames —](icordebugthread3-getactiveinternalframes-method.md) , aby zwrócić ramki wewnętrzne. (Ramki wewnętrzne to struktury danych wypychane na stosie przez środowisko uruchomieniowe do przechowywania danych tymczasowych).  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugStackWalk — Interfejs](icordebugstackwalk-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
