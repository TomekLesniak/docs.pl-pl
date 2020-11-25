---
title: ICorDebugBreakpoint, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
ms.openlocfilehash: 0c84a91c7da553d0c84a4995b4744576d861dcb9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730204"
---
# <a name="icordebugbreakpoint-interface"></a>ICorDebugBreakpoint, interfejs

Reprezentuje punkt przerwania w funkcji lub punkt obserwacji wartości.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Activate, metoda](icordebugbreakpoint-activate-method.md)|Ustawia stan aktywności tego elementu `ICorDebugBreakpoint` .|  
|[IsActive — Metoda](icordebugbreakpoint-isactive-method.md)|Pobiera wartość wskazującą, czy jest ona `ICorDebugBreakpoint` aktywna.|  
  
## <a name="remarks"></a>Uwagi  

 Punkty przerwania nie obsługują bezpośrednio wyrażeń warunkowych. Jeśli ta funkcja jest wymagana, debuger musi zaimplementować ją w górnej części `ICorDebugBreakpoint` .  
  
 Interfejs ICorDebugFunctionBreakpoint rozszerza `ICorDebugBreakpoint` obsługę punktów przerwania w funkcjach.  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
