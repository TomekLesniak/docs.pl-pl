---
title: IHostMemoryManager::GetMemoryLoad — Metoda
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
ms.openlocfilehash: 0611b82e22ec9d5d2cde2a7f46e65b5e25733610
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731361"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a>IHostMemoryManager::GetMemoryLoad — Metoda

Pobiera ilość pamięci fizycznej, która jest aktualnie używana, i dlatego jest niedostępna, zgodnie z informacjami o hoście.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pMemoryLoad`  
 określoną Wskaźnik do przybliżonej wartości procentowej całkowitej ilości pamięci fizycznej, która jest obecnie używana.  
  
 `pAvailableBytes`  
 określoną Wskaźnik do liczby bajtów dostępnych dla środowiska uruchomieniowego języka wspólnego (CLR).  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`GetMemoryLoad` pomyślnie zwrócono.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Uwagi  

 `GetMemoryLoad` Zawija `GlobalMemoryStatus` funkcję Win32. Wartość `pMemoryLoad` jest odpowiednikiem `dwMemoryLoad` pola w `MEMORYSTATUS` strukturze zwróconego z `GlobalMemoryStatus` .  
  
 Środowisko uruchomieniowe używa wartości zwracanej jako algorytmu heurystycznego modułu wyrzucania elementów bezużytecznych. Na przykład jeśli Host zgłasza, że większość pamięci jest w użyciu, Moduł wyrzucania elementów bezużytecznych może wybrać zbieranie z wielu generacji w celu zwiększenia ilości pamięci, która może być dostępna.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.GC?displayProperty=nameWithType>
- [IHostMemoryManager — Interfejs](ihostmemorymanager-interface.md)
