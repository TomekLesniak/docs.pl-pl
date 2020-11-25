---
title: IHostSyncManager::CreateSemaphore — Metoda
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
ms.openlocfilehash: 9af38a58ce8786c56d9f50089605dc994167497e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722131"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a>IHostSyncManager::CreateSemaphore — Metoda

Tworzy obiekt [IHostSemaphore](ihostsemaphore-interface.md) dla środowiska uruchomieniowego języka wspólnego (CLR) do użycia jako semafor dla zdarzeń oczekiwania.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `dwInitial`  
 podczas Początkowa liczba dla `ppSemaphore` .  
  
 `dwMax`  
 podczas Maksymalna liczba dla `ppSemaphore` .  
  
 `ppSemaphore`  
 określoną Wskaźnik do adresu `IHostSemaphore` wystąpienia lub wartość null, jeśli nie można utworzyć semafora.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`CreateSemaphore` pomyślnie zwrócono.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Za mało dostępnej pamięci, aby utworzyć żądany obiekt zdarzenia.|  
  
## <a name="remarks"></a>Uwagi  

 `CreateSemaphore` odzwierciedla funkcję Win32, która ma taką samą nazwę. `dwInitial`Parametry i `dwMax` używają tej samej semantyki jako `lInitialCount` odpowiednio Win32 i `lMaximumCount` Parameters. `dwInitial` musi zawierać się w przedziale od 0 do `dwMax` włącznie. `dwMax` musi być większa od zera.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRSyncManager — Interfejs](iclrsyncmanager-interface.md)
- [IHostSemaphore — Interfejs](ihostsemaphore-interface.md)
- [IHostSyncManager — Interfejs](ihostsyncmanager-interface.md)
