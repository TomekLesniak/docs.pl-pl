---
title: ICLRTask::SwitchIn — Metoda
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
ms.openlocfilehash: e98ae17d55c74d32844da96137c258d076ebc2db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691065"
---
# <a name="iclrtaskswitchin-method"></a>ICLRTask::SwitchIn — Metoda

Powiadamia środowisko uruchomieniowe języka wspólnego (CLR) o tym, że zadanie, które reprezentuje bieżące wystąpienie [ICLRTask](iclrtask-interface.md) , jest teraz w stanie nieobsługiwanym.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `threadHandle`  
 podczas Dojście do wątku fizycznego, w którym wykonywane jest zadanie reprezentowane przez bieżące `ICLRTask` wystąpienie.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`SwitchIn` pomyślnie zwrócono.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_INVALIDOPERATION|`SwitchIn` został wywołany bez wcześniejszego wywołania [metody SwitchOut —](iclrtask-switchout-method.md).|  
  
## <a name="remarks"></a>Uwagi  

 `threadHandle`Parametr reprezentuje dojście do wątku systemu operacyjnego, w którym zaplanowano zadanie reprezentowane przez bieżące `ICLRTask` wystąpienie. W przypadku wystąpienia personifikacji w tym wątku należy wywołać metodę [IHostSecurityManager:: RevertToSelf —](ihostsecuritymanager-reverttoself-method.md) przed przełączeniem w zadaniu.  
  
> [!NOTE]
> Wywołanie `SwitchIn` bez wcześniejszego wywołania do `SwitchOut` nie powiodło się z wartością HRESULT wynoszącą HOST_E_INVALIDOPERATION.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRTask — Interfejs](iclrtask-interface.md)
- [ICLRTaskManager — Interfejs](iclrtaskmanager-interface.md)
- [IHostTask — Interfejs](ihosttask-interface.md)
- [IHostTaskManager — Interfejs](ihosttaskmanager-interface.md)
