---
title: ESymbolReadingPolicy — Wyliczenie
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
ms.openlocfilehash: 42ce1f02294db98c5c593a5f16de5226703d5f9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733714"
---
# <a name="esymbolreadingpolicy-enumeration"></a>ESymbolReadingPolicy — Wyliczenie

Zawiera wartości, które ustawiają zasady odczytujące pliki bazy danych (PDB) programu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`eSymbolReadingAlways`|Określa, że debuger powinien zawsze odczytywać pliki PDB.|  
|`eSymbolReadingFullTrustOnly`|Określa, że debuger powinien odczytać tylko pliki PDB, które są skojarzone z zestawami pełnego zaufania.|  
|`eSymbolReadingNever`|Określa, że debuger nie powinien odczytywać plików PDB.|  
  
## <a name="remarks"></a>Uwagi  

 `ESymbolReadingPolicy`Wyliczenie jest używane z metodą [ICLRDebugManager:: SetSymbolReadingPolicy —](iclrdebugmanager-setsymbolreadingpolicy-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Hosting — Wyliczenia](hosting-enumerations.md)
