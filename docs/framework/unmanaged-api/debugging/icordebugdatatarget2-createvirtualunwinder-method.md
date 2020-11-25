---
title: Metoda ICorDebugDataTarget2::CreateVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: 0967b1cda86eab35015279edeed9a6b9852036b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713941"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a>Metoda ICorDebugDataTarget2::CreateVirtualUnwinder

Tworzy nowy wątek unwiatrer, który zaczyna odwracać od kontekstu początkowego (co nie musi być elementem liścia wątku).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a>Parametry  

 nativeThreadID  
 podczas Identyfikator wątku natywnego wątku, którego stos ma być rozłożony.  
  
 contextFlags  
 podczas Flagi określające, w których częściach kontekstu są zdefiniowane `initialContext` .  
  
 cbContext  
 podczas Rozmiar `initialContext` .  
  
 initialContext  
 podczas Dane w kontekście.  
  
 ppUnwinder  
 określoną Wskaźnik do adresu obiektu interfejsu ICorDebugVirtualUnwinder.  
  
## <a name="return-value"></a>Wartość zwracana  

 `S_OK` w przypadku powodzenia. Wszystkie inne `HRESULT` wskazuje na błąd. Wszystkie błędy `HRESULT` odebrane przez mscordbi są uznawane za krytyczne i powodują zwrócenie metod [ICorDebug](icordebug-interface.md) `CORDBG_E_DATA_TARGET_ERROR` .  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ta metoda jest dostępna tylko z .NET Native.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejs ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
