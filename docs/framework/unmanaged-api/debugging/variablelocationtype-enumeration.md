---
title: VariableLocationType, wyliczenie
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
ms.openlocfilehash: 1c65efa006a8b2f4fb4db257b4ad2cde99c4e75e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725264"
---
# <a name="variablelocationtype-enumeration"></a>VariableLocationType, wyliczenie

Wskazuje typ lokalizacji natywnej zmiennej.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,
    VLT_REGISTER_RELATIVE,
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`VLT_REGISTER`|Zmienna jest w rejestrze.|  
|`VLT_REGISTER_RELATIVE`|Zmienna znajduje się w lokalizacji pamięci względnej do rejestracji.|  
|`VLT_INVALID`|Zmienna nie jest przechowywana w rejestrze ani w lokalizacji pamięci względnej dla rejestru.|  
  
## <a name="remarks"></a>Uwagi  

 Element członkowski `VariableLocationType` wyliczenia jest zwracany przez metodę [ICorDebugVariableHome:: getlocationtype](icordebugvariablehome-getlocationtype-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — wyliczenia](debugging-enumerations.md)
