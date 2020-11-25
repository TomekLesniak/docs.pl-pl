---
title: CorSetENC — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
ms.openlocfilehash: df945803f2d56d04ccc68f314eb55665579ed7fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705985"
---
# <a name="corsetenc-enumeration"></a>CorSetENC — Wyliczenie

Zawiera wartości używane do wpływania na zachowanie podczas generowania metadanych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`MDSetENCOn`|Nieaktualne.|  
|`MDSetENCOff`|Nieaktualne.|  
|`MDUpdateENC`|Wskazuje, że metadane można zaktualizować, nie można przenieść tokenów.|  
|`MDUpdateFull`|Wskazuje, że tokeny mogą być przenoszone podczas aktualizacji.|  
|`MDUpdateExtension`|Wskazuje, że aktualizacje mogą obejmować tylko dodatki. Nie można przenieść tokenów.|  
|`MDUpdateIncremental`|Wskazuje, że kompilacja jest przyrostowa.|  
|`MDUpdateDelta`|Wskazuje, że powinny być zapisane tylko zmienione metadane.|  
|`MDUpdateMask`|Obejmuje `MDUpdateENC` `MDUpdateFull` i `MDUpdateIncremental` .|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorHdr. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Wyliczenia metadanych](metadata-enumerations.md)
