---
title: ICorDebugProcess5::GetGCHeapInformation — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
ms.openlocfilehash: 43054a71445193bae7a74e0ed6785cccd1d02dc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670995"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a>ICorDebugProcess5::GetGCHeapInformation — Metoda

Zawiera ogólne informacje o stercie wyrzucania elementów bezużytecznych, w tym o tym, czy jest obecnie wyliczalne.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pHeapInfo`  
 określoną Wskaźnik do wartości [COR_HEAPINFO](cor-heapinfo-structure.md) , która zawiera ogólne informacje o stercie wyrzucania elementów bezużytecznych.  
  
## <a name="remarks"></a>Uwagi  

 `ICorDebugProcess5::GetGCHeapInformation`Metoda musi zostać wywołana przed wyliczeniem sterty lub poszczególnych regionów sterty, aby upewnić się, że struktury wyrzucania elementów bezużytecznych w procesie są obecnie prawidłowe. Nie można przeprowadzić sterty odzyskiwania pamięci, gdy kolekcja jest w toku. W przeciwnym razie Wyliczenie może przechwytywać nieprawidłowe struktury wyrzucania elementów bezużytecznych.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugProcess5 — Interfejs](icordebugprocess5-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
