---
title: IHostTask — Interfejs
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
ms.openlocfilehash: 10efe853c9a7ad7676058bc01b07063c557623d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699225"
---
# <a name="ihosttask-interface"></a>IHostTask — Interfejs

Dostarcza metody, które umożliwiają środowisko uruchomieniowe języka wspólnego (CLR) komunikowanie się z hostem w celu zarządzania zadaniami.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Alert, metoda](ihosttask-alert-method.md)|Żąda, aby Host wznowił zadanie reprezentowane przez bieżące `IHostTask` wystąpienie, więc zadanie można przerwać.|  
|[GetPriority, metoda](ihosttask-getpriority-method.md)|Pobiera poziom priorytetu wątku zadania reprezentowanego przez bieżące `IHostTask` wystąpienie.|  
|[Join, metoda](ihosttask-join-method.md)|Blokuje zadanie wywołujące do momentu zakończenia zadania reprezentowanego przez bieżące `IHostTask` wystąpienie, upłynie określony przedział czasu lub [IHostTask:: Alert](ihosttask-alert-method.md) .|  
|[SetCLRTask, metoda](ihosttask-setclrtask-method.md)|Kojarzy wystąpienie [interfejsu ICLRTask](iclrtask-interface.md) z bieżącym `IHostTask` wystąpieniem.|  
|[SetPriority, metoda](ihosttask-setpriority-method.md)|Żądania, za pomocą których Host dostosowuje poziom priorytetu wątku dla zadania reprezentowanego przez bieżące `IHostTask` wystąpienie.|  
|[Start — Metoda](ihosttask-start-method.md)|Żąda, aby Host przeniesieł zadanie reprezentowane przez bieżące `IHostTask` wystąpienie ze stanu wstrzymania do stanu na żywo, w którym można wykonać kod.|  
  
## <a name="remarks"></a>Uwagi  

 Środowisko CLR wywołuje metody zdefiniowane przez, `IHostTask` Aby uruchomić zadanie, ustawić jego poziom priorytetu wątku i tak dalej.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRTask — Interfejs](iclrtask-interface.md)
- [ICLRTaskManager — Interfejs](iclrtaskmanager-interface.md)
- [IHostTaskManager — Interfejs](ihosttaskmanager-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
