---
title: 'ICorDebugVariableHome:: getregister — Metoda'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
ms.openlocfilehash: 7f912f4b13620b567f5aa097604e98112d85f02d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711757"
---
# <a name="icordebugvariablehomegetregister-method"></a>ICorDebugVariableHome:: getregister — Metoda

Pobiera rejestr zawierający zmienną z typem lokalizacji `VLT_REGISTER` i rejestr podstawowy dla zmiennej z typem lokalizacji `VLT_REGISTER_RELATIVE` .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pRegister`  
 określoną Wartość wyliczenia CorDebugRegister —, która wskazuje rejestr dla zmiennej z typem lokalizacji `VLT_REGISTER` i rejestr podstawowy dla zmiennej z typem lokalizacji `VLT_REGISTER_RELATIVE` .  
  
## <a name="return-value"></a>Wartość zwracana  

 Metoda zwraca następujące wartości:  
  
|Wartość|Opis|  
|-----------|-----------------|  
|`S_OK`|Zmienna znajduje się w rejestrze wskazanym przez `pRegister` argument.|  
|`E_FAIL`|Zmienna nie znajduje się w rejestrze ani w lokalizacji względnej do rejestracji.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [VariableLocationType, wyliczenie](variablelocationtype-enumeration.md)
- [ICorDebugVariableHome, interfejs](icordebugvariablehome-interface.md)
