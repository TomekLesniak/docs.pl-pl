---
title: USER_THREAD — Struktura
ms.date: 03/30/2017
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
ms.openlocfilehash: 409651aa69e957418ad46f61e1bd57add0eb10a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722898"
---
# <a name="user_thread-structure"></a>USER_THREAD — Struktura

Zawiera informacje dotyczące debugera wątku. Aby uzyskać więcej informacji, zobacz metodę [INotifySource2:: SetNotifyFilter —](inotifysource2-setnotifyfilter-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`pSidBuffer`|Adres buforu wątku.|  
|`dwSidLen`|Długość buforu wątku w bajtach.|  
|`dwTid`|Identyfikator wątku.|  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Zobacz także

- [SetNotifyFilter, metoda](inotifysource2-setnotifyfilter-method.md)
- [Struktury magazynu symboli diagnostycznych](diagnostics-symbol-store-structures.md)
