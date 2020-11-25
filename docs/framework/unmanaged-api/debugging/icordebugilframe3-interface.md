---
title: ICorDebugILFrame3 — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 15212cb5-93d4-4025-bec9-d4b9919eb1fe
topic_type:
- apiref
ms.openlocfilehash: dab5329086971b9349deaf84535fa251744f3cf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724991"
---
# <a name="icordebugilframe3-interface"></a>ICorDebugILFrame3 — Interfejs

Dostarcza metodę, która hermetyzuje wartość zwracaną przez funkcję. `ICorDebugILFrame3` jest logicznym rozszerzeniem interfejsów ICorDebugILFrame i ICorDebugILFrame2.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetReturnValueForILOffset, metoda](icordebugilframe3-getreturnvalueforiloffset-method.md)|Pobiera obiekt ICorDebugValue, który hermetyzuje zwracaną wartość funkcji.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugCode3 — Interfejs](icordebugcode3-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
