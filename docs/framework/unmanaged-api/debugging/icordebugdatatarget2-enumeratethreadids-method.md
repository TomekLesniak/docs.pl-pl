---
title: Metoda ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 31a839076b34901ae1a8f3b43021f64f77629fc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713850"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a>Metoda ICorDebugDataTarget2::EnumerateThreadIDs

Zwraca listę aktywnych identyfikatorów wątków.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a>Parametry  

 cThreadIDs  
 podczas Maksymalna liczba wątków, których identyfikatory można zwrócić.  
  
 pcThreadIds  
 określoną Wskaźnik `ULONG32` wskazujący rzeczywistą liczbę identyfikatorów wątków zapisaną w `pThreadIds` tablicy.  
  
 pThreadIDs  
 Tablica identyfikatorów wątków.  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ta metoda jest dostępna tylko z .NET Native.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md). **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejs ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
