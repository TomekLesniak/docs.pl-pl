---
title: HOST_TYPE — Wyliczenie
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
ms.openlocfilehash: 31640ada28af8e35554b91d5931d427fbaa8dcbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721858"
---
# <a name="host_type-enumeration"></a>HOST_TYPE — Wyliczenie

Zawiera wartości określające typ hosta, który uruchamia aplikację.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|Uruchom aplikację z AppLaunch.exe.<br /><br /> Ta wartość jest używana w przypadku aplikacji częściowo zaufanych.|  
|`HOST_TYPE_CORFLAG`|Uruchom aplikację bezpośrednio. Oznacza to, że należy uruchomić aplikację z własnego pliku. exe.<br /><br /> Ta wartość jest używana w przypadku w pełni zaufanych aplikacji.|  
|`HOST_TYPE_DEFAULT`|Taki sam jak HOST_TYPE_APPLAUNCH.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Hosting — Wyliczenia](hosting-enumerations.md)
