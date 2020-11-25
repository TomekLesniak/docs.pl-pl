---
title: ICorDebugGuidToTypeEnum — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
ms.openlocfilehash: 149c5b09639c8809e736ade09566e7b1b530e3eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705718"
---
# <a name="icordebugguidtotypeenum-interface"></a>ICorDebugGuidToTypeEnum — Interfejs

Dostarcza moduł wyliczający, który definiuje mapowanie między zestawem identyfikatorów GUID i odpowiadającymi im typami, które są reprezentowane przez wystąpienia ICorDebugType. Ten interfejs dziedziczy metody z interfejsu ICorDebugEnum.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[ICorDebugGuidToTypeEnum:: Next](icordebugguidtotypeenum-next-method.md)|Pobiera określoną liczbę wystąpień [CorDebugGuidToTypeMapping —](cordebugguidtotypemapping-structure.md) , które MAPUJĄ identyfikatory GUID na informacje o typie.|  
  
## <a name="remarks"></a>Uwagi  

 `ICorDebugGuidToTypeEnum`Obiekt interfejsu można pobrać, wywołując metodę [ICorDebugAppDomain3:: GetCachedWinRTTypes —](icordebugappdomain3-getcachedwinrttypes-method.md) . Debuger może wywołać [kolejną](icordebugguidtotypeenum-next-method.md) metodę tego interfejsu, aby pobrać obiekty [CorDebugGuidToTypeMapping —](cordebugguidtotypemapping-structure.md) reprezentujące mapowania zarządzanych reprezentacji typów środowisko wykonawcze systemu Windows załadowanych w domenie aplikacji używanej do wywołania metody [ICorDebugAppDomain3:: GetCachedWinRTTypes —](icordebugappdomain3-getcachedwinrttypes-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** środowisko wykonawcze systemu Windows  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
