---
title: CorDebugExceptionFlags — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorDebugExceptionFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionFlags
helpviewer_keywords:
- CorDebugExceptionFlags enumeration [.NET Framework debugging]
ms.assetid: b22687a8-e9cf-4e65-a1b0-f92a81bc524e
topic_type:
- apiref
ms.openlocfilehash: a50272bce2e27963a1d684fef40bac30cf44e1f0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712719"
---
# <a name="cordebugexceptionflags-enumeration"></a>CorDebugExceptionFlags — Wyliczenie

Zawiera dodatkowe informacje o wyjątku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|Nie istnieje żaden wyjątek.|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|Wyjątek jest przechwytywany.<br /><br /> Czas wyjątku może być nadal taki, aby debuger nie mógł go przechwycić. Na przykład, jeśli nie istnieje kod zarządzany poniżej bieżącego wywołania zwrotnego lub zdarzenie wyjątku spowodowało z załącznika just-in-Time (JIT), nie można przechwycić wyjątku.|  
  
## <a name="remarks"></a>Uwagi  

 Nowe wartości można dodać do tego wyliczenia w nowszych wersjach, dlatego należy przygotować kod, który używa `CorDebugExceptionFlags` dla nieoczekiwanych wartości.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — wyliczenia](debugging-enumerations.md)
