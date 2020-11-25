---
title: 'ICorDebugVariableHome:: getlocationtype — Metoda'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
ms.openlocfilehash: 3979ed19f8a61ac1fc045b83c52e23d7255ac364
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711874"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a>ICorDebugVariableHome:: getlocationtype — Metoda

Pobiera typ lokalizacji natywnej zmiennej.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pLocationType`  
 określoną Wskaźnik do typu lokalizacji natywnej zmiennej.  Aby uzyskać więcej informacji, zobacz Wyliczenie [VariableLocationType](variablelocationtype-enumeration.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugVariableHome, interfejs](icordebugvariablehome-interface.md)
- [VariableLocationType, wyliczenie](variablelocationtype-enumeration.md)
