---
title: CALL_ID — Struktura
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
ms.openlocfilehash: 3f41dd969e25f7a42308ff0b7b2d617344284b38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725251"
---
# <a name="call_id-structure"></a>CALL_ID — Struktura

Dostarcza informacje do debugera dotyczące funkcji, która jest wywoływana. Aby uzyskać więcej informacji, zobacz Interfejs [INotifySink2](inotifysink2-interface.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`szMachine`|Identyfikuje maszynę, która wywołuje wywołanie.|  
|`dwPid`|Identyfikuje procesor maszyny.|  
|`pUserThread`|Identyfikuje wątek wykonujący wywołanie.|  
|`addrStackPointer`|Określa adres stosu wywołań.|  
|`szEntryPoint`|Określa adres wywołania.|  
|`szDestinationMachine`|Identyfikuje maszynę, która będzie wykonywać wywołanie.|  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Zobacz także

- [INotifySink2 — Interfejs](inotifysink2-interface.md)
- [Struktury magazynu symboli diagnostycznych](diagnostics-symbol-store-structures.md)
