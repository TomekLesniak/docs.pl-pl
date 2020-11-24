---
title: ICLRTask — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask
helpviewer_keywords:
- ICLRTask interface [.NET Framework hosting]
ms.assetid: b3a44df3-578a-4451-b55e-70c8e7695f5e
topic_type:
- apiref
ms.openlocfilehash: 5ecc42950775a620796a1c775e5f088f461a12c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690827"
---
# <a name="iclrtask-interface"></a>ICLRTask — Interfejs

Dostarcza metody, które umożliwiają hostowi wykonywanie żądań środowiska uruchomieniowego języka wspólnego (CLR) lub dostarczenie do środowiska CLR powiadomienia o skojarzonym zadaniu.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Abort — Metoda](iclrtask-abort-method.md)|Żąda, aby środowisko CLR przerywał zadanie reprezentowane przez bieżące `ICLRTask` wystąpienie.|  
|[ExitTask, metoda](iclrtask-exittask-method.md)|Powiadamia środowisko CLR, że zadanie skojarzone z bieżącym `ICLRTask` wystąpieniem kończy działanie i próbuje bezpiecznie zamknąć zadanie.|  
|[GetMemStats, metoda](iclrtask-getmemstats-method.md)|Pobiera informacje statystyczne dotyczące korzystania z zasobów pamięci przez zadanie reprezentowane przez bieżące `ICLRTask` wystąpienie.|  
|[LocksHeld, metoda](iclrtask-locksheld-method.md)|Pobiera liczbę blokad aktualnie przechowywanych w zadaniu.|  
|[NeedsPriorityScheduling, metoda](iclrtask-needspriorityscheduling-method.md)|Pobiera wartość wskazującą, czy host powinien przypisać wysoki priorytet, aby ponownie zaplanować zadanie reprezentowane przez bieżące `ICLRTask` wystąpienie.|  
|[Reset — Metoda](iclrtask-reset-method.md)|Informuje środowisko CLR, że host ukończył zadanie, i włącza środowisko CLR do ponownego użycia bieżącego `ICLRTask` wystąpienia, aby reprezentować inne zadanie.|  
|[RudeAbort — Metoda](iclrtask-rudeabort-method.md)|Powoduje, że środowisko CLR przerywa zadanie reprezentowane przez bieżące `ICLRTask` wystąpienie natychmiast, bez gwarancji, że finalizatory zostaną wykonane.|  
|[SetTaskIdentifier, metoda](iclrtask-settaskidentifier-method.md)|Ustawia unikatowy identyfikator zadania reprezentowanego przez bieżące `ICLRTask` wystąpienie do użycia podczas debugowania.|  
|[SwitchIn, metoda](iclrtask-switchin-method.md)|Powiadamia środowisko CLR, że zadanie reprezentowane przez bieżące `ICLRTask` wystąpienie jest w stanie nieobsługiwanym.|  
|[SwitchOut, metoda](iclrtask-switchout-method.md)|Powiadamia środowisko CLR, że zadanie reprezentowane przez bieżące `ICLRTask` wystąpienie nie jest już w stanie obsługiwanym.|  
|[YieldTask, metoda](iclrtask-yieldtask-method.md)|Żąda, aby środowisko CLR udostępnić czas procesora innym zadanie. Środowisko CLR nie gwarantuje, że zadanie zostanie umieszczone w stanie, w którym może dać czas przetwarzania.|  
  
## <a name="remarks"></a>Uwagi  

 `ICLRTask`Jest reprezentacją zadania dla środowiska CLR. W dowolnym momencie wykonywania kodu zadanie można opisać jako uruchomione lub oczekiwanie na uruchomienie. Host wywołuje metodę w `ICLRTask::SwitchIn` celu powiadomienia środowiska CLR o tym, że zadanie reprezentowane przez bieżące `ICLRTask` wystąpienie jest teraz w stanie interoperacyjnym. Po wywołaniu `ICLRTask::SwitchIn` , host może zaplanować zadanie w dowolnym wątku systemu operacyjnego, z wyjątkiem przypadków, gdy środowisko uruchomieniowe wymaga koligacji wątków, jak określono przez wywołania metod [IHostTaskManager:: BeginThreadAffinity —](ihosttaskmanager-beginthreadaffinity-method.md) i [IHostTaskManager:: EndThreadAffinity —](ihosttaskmanager-endthreadaffinity-method.md) . Czasami system operacyjny może zdecydować się na usunięcie zadania z wątku i umieszczenie go w stanie nieuruchomionym. Na przykład może się to zdarzyć, gdy zadanie jest blokowane w przypadku elementów pierwotnych synchronizacji lub czeka na ukończenie operacji we/wy. Host wywołuje [SwitchOut —](iclrtask-switchout-method.md) w celu powiadomienia środowiska CLR, że zadanie reprezentowane przez bieżące `ICLRTask` wystąpienie nie jest już w stanie nieobsługiwanym.  
  
 Zadanie zwykle kończy się na końcu wykonywania kodu. W tym czasie Host wywołuje, `ICLRTask::ExitTask` aby zniszczyć skojarzone `ICLRTask` . Zadania mogą być również odtwarzane przy użyciu wywołania do `ICLRTask::Reset` , co umożliwia `ICLRTask` ponowne użycie wystąpienia. Takie podejście uniemożliwia narzutowanie wielokrotnego tworzenia i niszczenia wystąpień.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRTaskManager — Interfejs](iclrtaskmanager-interface.md)
- [IHostTask — Interfejs](ihosttask-interface.md)
- [IHostTaskManager — Interfejs](ihosttaskmanager-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
- [ICLRTask2 — Interfejs](iclrtask2-interface.md)
