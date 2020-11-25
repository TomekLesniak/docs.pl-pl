---
title: IHostIoCompletionManager — Interfejs
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
ms.openlocfilehash: 75ad8670008242008aa344835143ff9b2add0a6c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719596"
---
# <a name="ihostiocompletionmanager-interface"></a>IHostIoCompletionManager — Interfejs

Dostarcza metody, które umożliwiają środowisko uruchomieniowe języka wspólnego (CLR) do współdziałania z portami zakończenia we/wy dostarczonymi przez hosta.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Bind, metoda](ihostiocompletionmanager-bind-method.md)|Tworzy powiązanie dojścia do portu zakończenia we/wy.|  
|[CloseIoCompletionPort, metoda](ihostiocompletionmanager-closeiocompletionport-method.md)|Zamyka port, który został utworzony za pomocą wcześniejszego wywołania do `CreateIoCompletionPort` .|  
|[CreateIoCompletionPort, metoda](ihostiocompletionmanager-createiocompletionport-method.md)|Żąda utworzenia przez hosta nowego portu zakończenia we/wy.|  
|[GetAvailableThreads, metoda](ihostiocompletionmanager-getavailablethreads-method.md)|Pobiera liczbę wątków zakończenia we/wy, które nie przetwarzają obecnie żądań.|  
|[GetHostOverlappedSize, metoda](ihostiocompletionmanager-gethostoverlappedsize-method.md)|Pobiera rozmiar danych niestandardowych, które Host zamierza dołączyć do żądań we/wy.|  
|[GetMaxThreads, metoda](ihostiocompletionmanager-getmaxthreads-method.md)|Pobiera maksymalną liczbę wątków, które host może przydzielić do żądań we/wy usługi.|  
|[GetMinThreads, metoda](ihostiocompletionmanager-getminthreads-method.md)|Pobiera minimalną liczbę wątków przemieszczonych przez hosta w celu obsługi żądań we/wy.|  
|[InitializeHostOverlapped, metoda](ihostiocompletionmanager-initializehostoverlapped-method.md)|Udostępnia hostowi możliwość zainicjowania wszelkich niestandardowych danych dotyczących żądania we/wy.|  
|[SetCLRIoCompletionManager, metoda](ihostiocompletionmanager-setclriocompletionmanager-method.md)|Dostarcza host ze wskaźnikiem interfejsu do wystąpienia [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) zaimplementowanego przez środowisko CLR.|  
|[SetMaxThreads, metoda](ihostiocompletionmanager-setmaxthreads-method.md)|Ustawia maksymalną liczbę wątków przynoszących Host do obsługi żądań we/wy.|  
|[SetMinThreads, metoda](ihostiocompletionmanager-setminthreads-method.md)|Ustawia minimalną liczbę wątków, które host powinien przydzielić do zakończenia operacji we/wy.|  
  
## <a name="remarks"></a>Uwagi  

 `IHostIoCompletionManager` odnosi się do `ICLRIoCompletionManager` interfejsu implementowanego przez środowisko CLR. Środowisko CLR wywołuje metody `IHostIoCompletionManager` w celu powiązania dojść z portami dostarczanymi przez hosta, a host wywołuje metody `ICLRIoCompletionManager` w celu zgłaszania ukończenia żądań we/wy.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Hosting — Interfejsy](hosting-interfaces.md)
