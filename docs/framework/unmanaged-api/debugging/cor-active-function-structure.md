---
title: COR_ACTIVE_FUNCTION — Struktura
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
ms.openlocfilehash: c50ba530d78296ebb956329b2f34b4f1e5cae94c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727422"
---
# <a name="cor_active_function-structure"></a>COR_ACTIVE_FUNCTION — Struktura

Zawiera informacje o funkcjach, które są obecnie aktywne w ramkach wątku. Ta struktura jest używana przez metodę [ICorDebugThread2:: GetActiveFunctions —](icordebugthread2-getactivefunctions-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`pAppDomain`|Wskaźnik do właściciela domeny aplikacji `ilOffset` pola.|  
|`pModule`|Wskaźnik do właściciela modułu `ilOffset` pola.|  
|`pFunction`|Wskaźnik do właściciela funkcji `ilOffset` pola.|  
|`ilOffset`|Przesunięcie języka pośredniego (MSIL) firmy Microsoft dla ramki.|  
|`flags`|Zarezerwowane do użytku w przyszłości.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Struktury debugowania](debugging-structures.md)
- [Debugowanie](index.md)
