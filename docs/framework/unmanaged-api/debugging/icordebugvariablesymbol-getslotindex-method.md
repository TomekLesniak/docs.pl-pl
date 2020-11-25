---
title: 'ICorDebugVariableSymbol:: GetSlotIndex, Metoda'
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: fc42517cb95dfc14c472b5bb9111ebd70639cee7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725992"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a>ICorDebugVariableSymbol:: GetSlotIndex, Metoda

Pobiera indeks gniazda zarządzanego zmiennej lokalnej.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pSlotIndex`  
 określoną Wskaźnik do indeksu gniazda zmiennej lokalnej.  
  
## <a name="return-value"></a>Wartość zwracana  

 `S_OK` w przypadku powodzenia. `E_FAIL` Jeśli zmienna jest argumentem funkcji.  
  
## <a name="remarks"></a>Uwagi  

 Do pobrania informacji o metadanych zmiennej można użyć indeksu gniazda zarządzanego zmiennej lokalnej.  
  
> [!NOTE]
> Ta metoda jest dostępna tylko z .NET Native.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugVariableSymbol, interfejs](icordebugvariablesymbol-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
