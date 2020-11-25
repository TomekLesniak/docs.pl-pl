---
title: CorDebugHandleType — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorDebugHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugHandleType
helpviewer_keywords:
- CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type:
- apiref
ms.openlocfilehash: a0ec83a5590e184b9ff60449a8147d1a3c90a6a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712459"
---
# <a name="cordebughandletype-enumeration"></a>CorDebugHandleType — Wyliczenie

Wskazuje typ dojścia.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`HANDLE_STRONG`|Dojście jest silnie, co uniemożliwia odjęcie obiektu przez wyrzucanie elementów bezużytecznych.|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|Dojście jest słabe, co nie zapobiega odzyskiwaniu obiektu przez wyrzucanie elementów bezużytecznych.<br /><br /> Uchwyt jest nieprawidłowy, gdy zbierany jest obiekt.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — wyliczenia](debugging-enumerations.md)
