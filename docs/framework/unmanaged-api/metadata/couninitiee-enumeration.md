---
title: COUNINITIEE — Wyliczenie
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
ms.openlocfilehash: b0f8c7e6d2acf4d4c080cc147bf6d42bf13cb51b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723834"
---
# <a name="couninitiee-enumeration"></a>COUNINITIEE — Wyliczenie

Określa stałe używane przez [CoUninitializeEE —](../hosting/couninitializeee-function.md) podczas inicjowania środowiska uruchomieniowego języka wspólnego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|Wskazuje domyślny tryb uninicjującym.|  
|`COUNINITEE_DLL`|Wskazuje tryb odinicjowania w przypadku zwalniania zestawu.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Wyliczenia metadanych](metadata-enumerations.md)
