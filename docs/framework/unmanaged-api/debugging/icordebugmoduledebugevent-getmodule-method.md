---
title: 'ICorDebugModuleDebugEvent:: GetModule — Metoda'
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: ec23cda02ff689a3365fe96fb5280054a9795caa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709508"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a>ICorDebugModuleDebugEvent:: GetModule — Metoda

Pobiera scalony moduł, który został właśnie załadowany lub zwolniony.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppModule`  
 określoną Wskaźnik do adresu obiektu ICorDebugModule, który reprezentuje scalony moduł, który został właśnie załadowany lub zwolniony.  
  
## <a name="remarks"></a>Uwagi  

 Można wywołać metodę [GetEventKind](icordebugdebugevent-geteventkind-method.md) , aby określić, czy moduł został załadowany, czy zwolniony.  
  
> [!NOTE]
> Ta metoda jest dostępna tylko z .NET Native.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugModuleDebugEvent, interfejs](icordebugmoduledebugevent-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
