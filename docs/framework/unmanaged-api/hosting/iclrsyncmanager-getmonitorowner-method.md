---
title: ICLRSyncManager::GetMonitorOwner — Metoda
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
ms.openlocfilehash: a2cb82d8071518af4d4bc3276871f3846a5a5693
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687089"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a>ICLRSyncManager::GetMonitorOwner — Metoda

Pobiera wystąpienie [IHostTask](ihosttask-interface.md) , które jest właścicielem monitora identyfikowanego przez określony plik cookie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `cookie`  
 podczas Plik cookie skojarzony z monitorem.  
  
 `ppOwnerHostTask`  
 określoną Wskaźnik do elementu, `IHostTask` który jest aktualnie właścicielem monitora lub ma wartość null, jeśli żadne zadanie nie ma własności.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`GetMonitorOwner` pomyślnie zwrócono.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Uwagi  

 Host zazwyczaj wywołuje `GetMonitorOwner` jako część mechanizmu wykrywania zakleszczenia. Plik cookie jest skojarzony z monitorem, gdy jest tworzony przy użyciu wywołania do [IHostSyncManager:: CreateMonitorEvent —](ihostsyncmanager-createmonitorevent-method.md).  
  
> [!NOTE]
> Wywołanie do zwolnienia zdarzenia podstawowego monitora może być blokowane — ale nie będzie zakleszczenie — Jeśli wywołanie tej metody jest obecnie stosowane dla pliku cookie skojarzonego z tym monitorem. Inne zadania mogą być również blokowane, jeśli próbują uzyskać ten monitor.  
  
 `GetMonitorOwner` zawsze zwraca natychmiast i może być wywoływana w dowolnym momencie po wywołaniu `CreateMonitorEvent` . Host nie musi czekać, aż zadanie oczekuje na zdarzenie.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRSyncManager — Interfejs](iclrsyncmanager-interface.md)
- [IHostSyncManager — Interfejs](ihostsyncmanager-interface.md)
