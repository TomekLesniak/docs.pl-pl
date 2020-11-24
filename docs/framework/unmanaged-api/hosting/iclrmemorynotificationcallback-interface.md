---
title: ICLRMemoryNotificationCallback — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
ms.openlocfilehash: 5762a354bec485cb382b5460dfd2a337f79bee1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689540"
---
# <a name="iclrmemorynotificationcallback-interface"></a>ICLRMemoryNotificationCallback — Interfejs

Umożliwia hostowi zgłaszanie warunków ciśnienia pamięci przy użyciu podejścia podobnego do `CreateMemoryResourceNotification` funkcji Win32.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[OnMemoryNotification, metoda](iclrmemorynotificationcallback-onmemorynotification-method.md)|Powiadamia środowisko uruchomieniowe języka wspólnego (CLR) o załadowaniu pamięci na komputerze.|  
  
## <a name="remarks"></a>Uwagi  

 Host używa `ICLRMemoryNotificationCallback` interfejsu do żądania zasobów wolnej pamięci środowiska CLR.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IHostMemoryManager — Interfejs](ihostmemorymanager-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
