---
title: CorDebugUnmappedStop — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
ms.openlocfilehash: e251bf67adcaf2bbd6565eda068d487eb0d70efd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725778"
---
# <a name="cordebugunmappedstop-enumeration"></a>CorDebugUnmappedStop — Wyliczenie

Określa typ niezamapowanego kodu, który może wyzwolić zatrzymanie w wykonaniu kodu przez stepper.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`STOP_NONE`|Nie należy Zatrzymywać w żadnym typie niezamapowanego kodu.|  
|`STOP_PROLOG`|Zatrzymaj w kodzie prologu.|  
|`STOP_EPILOG`|Zatrzymywanie w kodzie epilogu.|  
|`STOP_NO_MAPPING_INFO`|Zatrzymaj w kodzie, który nie zawiera informacji dotyczących mapowania.|  
|`STOP_OTHER_UNMAPPED`|Zatrzymaj w niemapowanym kodzie, który nie mieści się w niezgodnej kategorii Prolog, epilogu, Brak-mapowania-informacje lub niezarządzana.|  
|`STOP_UNMANAGED`|Zatrzymaj w kodzie niezarządzanym. Ta wartość jest prawidłowa tylko w przypadku debugowania międzyoperacyjności.|  
|`STOP_ALL`|Zatrzymaj wszystkie typy niezamapowanego kodu.|  
  
## <a name="remarks"></a>Uwagi  

 Użyj metody [ICorDebugStepper:: SetUnmappedStopMask —](icordebugstepper-setunmappedstopmask-method.md) , aby ustawić flagi określające niezamapowany kod, w którym zostanie zatrzymany stepper.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — wyliczenia](debugging-enumerations.md)
