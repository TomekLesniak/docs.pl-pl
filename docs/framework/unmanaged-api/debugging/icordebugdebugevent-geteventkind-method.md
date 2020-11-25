---
title: Metoda ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 7876dc6ec5ecee52b64e54e1c42533f8348e4dc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713681"
---
# <a name="icordebugdebugeventgeteventkind-method"></a>Metoda ICorDebugDebugEvent::GetEventKind

Wskazuje, jaki rodzaj zdarzenia `ICorDebugDebugEvent` reprezentuje ten obiekt.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a>Parametry  

 pDebugEventKind  
 Wskaźnik do elementu członkowskiego wyliczenia [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) , który wskazuje typ zdarzenia.  
  
## <a name="remarks"></a>Uwagi  

 Na podstawie wartości, można `pDebugEventKind` wywołać, `QueryInterface` Aby uzyskać dokładniejszy interfejs zdarzenia debugowania, który zawiera dodatkowe dane.  
  
> [!NOTE]
> Ta metoda jest dostępna tylko z .NET Native.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejs ICorDebugDebugEvent](icordebugdebugevent-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
