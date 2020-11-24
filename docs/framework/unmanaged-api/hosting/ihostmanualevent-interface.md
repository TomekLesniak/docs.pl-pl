---
title: IHostManualEvent — Interfejs
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 50e37b770e3ee6e0a5cdfca61fc5b09749e5735f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673206"
---
# <a name="ihostmanualevent-interface"></a>IHostManualEvent — Interfejs

Zapewnia implementację hosta reprezentacji zdarzenia resetowania ręcznego.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Reset — Metoda](ihostmanualevent-reset-method.md)|Resetuje bieżące `IHostManualEvent` wystąpienie do stanu niesygnalizującego.|  
|[Set, metoda](ihostmanualevent-set-method.md)|Ustawia bieżące `IHostManualEvent` wystąpienie na sygnał.|  
|[Wait — Metoda](ihostmanualevent-wait-method.md)|Powoduje, że bieżące `IHostManualEvent` wystąpienie zaczeka, aż będzie jego właścicielem lub upłynie określony czas.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRSyncManager — Interfejs](iclrsyncmanager-interface.md)
- [IHostAutoEvent — Interfejs](ihostautoevent-interface.md)
- [IHostSemaphore — Interfejs](ihostsemaphore-interface.md)
- [IHostSyncManager — Interfejs](ihostsyncmanager-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
