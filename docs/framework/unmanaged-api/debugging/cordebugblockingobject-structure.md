---
title: CorDebugBlockingObject — Struktura
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
ms.openlocfilehash: b16feb1af0d4975411876e78940d21096750d2ae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726590"
---
# <a name="cordebugblockingobject-structure"></a>CorDebugBlockingObject — Struktura

Definiuje obiekt, który blokuje wątek i konkretną przyczynę zablokowania wątku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`pBlockingObject`|Obiekt, na którym jest blokowany wątek. Ten obiekt jest prawidłowy tylko dla czasu trwania bieżącego zsynchronizowanego stanu. Jeśli dwa wątki blokują ten sam obiekt w tym samym stanie zsynchronizowanym, można oczekiwać, że metoda [ICorDebugValue:: GetAddress](icordebugvalue-getaddress-method.md) zwraca tę samą wartość. Jednak interfejsy mogą lub nie mogą być odpowiednikami wskaźnika.|  
|`dwTimeout`|Liczba milisekund przed upływem limitu czasu operacji blokowania lub wartość NIESKOŃCZONość, która wskazuje, że nie przekroczy limitu czasu. Wartość limitu czasu określa łączny czas trwania operacji blokowania, a nie czas, który jest nadal pozostały.|  
|`blockingReason`|Przyczyna blokowania wątku dla tego obiektu.|  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Struktury debugowania](debugging-structures.md)
- [Debugowanie](index.md)
