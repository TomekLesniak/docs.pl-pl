---
title: ICLRSyncManager — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
ms.openlocfilehash: 5bfab21a36becf943b1813f266cf70c4b5e5b1d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690996"
---
# <a name="iclrsyncmanager-interface"></a>ICLRSyncManager — Interfejs

Definiuje metody, które pozwalają hostowi uzyskać informacje o żądanych zadaniach i wykryć zakleszczenie w swojej implementacji synchronizacji.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[CreateRWLockOwnerIterator, metoda](iclrsyncmanager-createrwlockowneriterator-method.md)|Żądania, które środowisko uruchomieniowe języka wspólnego (CLR) tworzy iterator dla hosta do użycia w celu określenia zestawu zadań oczekujących na blokadę modułu odczytującego.|  
|[DeleteRWLockOwnerIterator, metoda](iclrsyncmanager-deleterwlockowneriterator-method.md)|Żądania, aby środowisko CLR zniszczyć iterator, który został utworzony przez wywołanie metody `CreateRWLockOwnerIterator` .|  
|[GetMonitorOwner, metoda](iclrsyncmanager-getmonitorowner-method.md)|Pobiera zadanie, które jest właścicielem określonego monitora.|  
|[GetRWLockOwnerNext, metoda](iclrsyncmanager-getrwlockownernext-method.md)|Pobiera następne zadanie czekające na bieżącą blokadę modułu odczytującego.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Threading.Thread>
- [IHostSyncManager — Interfejs](ihostsyncmanager-interface.md)
- [Wątki zarządzane i niezarządzane](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [Hosting — Interfejsy](hosting-interfaces.md)
