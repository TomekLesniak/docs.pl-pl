---
title: IHostTaskManager::ReverseLeaveRuntime — Metoda
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseLeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type:
- apiref
ms.openlocfilehash: ea352b189d65e0be6a2bbc81c19a03d1edd8143d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554804"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a>IHostTaskManager::ReverseLeaveRuntime — Metoda
Powiadamia hosta, że kontrola opuszcza środowisko uruchomieniowe języka wspólnego (CLR) i wprowadza niezarządzaną funkcję, która była z kolei wywoływana z kodu zarządzanego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`ReverseLeaveRuntime` pomyślnie zwrócono.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Za mało dostępnej pamięci, aby zakończyć żądaną alokację zasobów.|  
  
## <a name="remarks"></a>Uwagi  
 Środowisko CLR wywołuje, `ReverseLeaveRuntime` aby poinformować hosta, że aktualnie wykonywane zadanie zwraca kontrolę do niezarządzanej funkcji, która była z kolei wywoływana z kodu zarządzanego za pośrednictwem wywołania platformy. Każde wywołanie `ReverseLeaveRuntime` dopasowuje odpowiednie wywołanie do [ReverseEnterRuntime —](ihosttaskmanager-reverseenterruntime-method.md).  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [CallNeedsHostHook, metoda](ihosttaskmanager-callneedshosthook-method.md)
- [EnterRuntime, metoda](ihosttaskmanager-enterruntime-method.md)
- [ICLRTask — Interfejs](iclrtask-interface.md)
- [ICLRTaskManager — Interfejs](iclrtaskmanager-interface.md)
- [IHostTask — Interfejs](ihosttask-interface.md)
- [IHostTaskManager — Interfejs](ihosttaskmanager-interface.md)
- [LeaveRuntime, metoda](ihosttaskmanager-leaveruntime-method.md)
- [Bliższe spojrzenie na wywołanie platformy](/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))
