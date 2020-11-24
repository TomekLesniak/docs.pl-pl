---
title: ICLRGCManager::GetStats — Metoda
ms.date: 03/30/2017
api_name:
- ICLRGCManager.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type:
- apiref
ms.openlocfilehash: 70fe8b132f03925c41b6bc7aae8e60fea1b05202
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678301"
---
# <a name="iclrgcmanagergetstats-method"></a>ICLRGCManager::GetStats — Metoda

Pobiera zestaw bieżących statystyk dotyczących systemu odzyskiwania pamięci środowiska uruchomieniowego języka wspólnego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pStats`  
 [in. out] Wystąpienie [COR_GC_STATS](cor-gc-stats-structure.md) , które zawiera żądane dane statystyczne.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`GetStats` pomyślnie zwrócono.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Uwagi  

 Środowisko CLR oblicza i zwraca tylko te statystyki, które są określone w `Flags` polu `pStats` .  
  
 Ustaw wartość `Flags` pola na co najmniej jedną wartość wyliczenia [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) , aby określić, które statystyki w strukturze [COR_GC_STATS](cor-gc-stats-structure.md) mają być ustawione.  
  
 Przykładem użycia jest następujący:  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Automatyczne zarządzanie pamięcią](../../../standard/automatic-memory-management.md)
- [COR_GC_STATS — Struktura](cor-gc-stats-structure.md)
- [COR_GC_STAT_TYPES — Wyliczenie](cor-gc-stat-types-enumeration.md)
- [Odzyskiwanie pamięci](../../../standard/garbage-collection/index.md)
- [ICLRControl — Interfejs](iclrcontrol-interface.md)
- [ICLRGCManager — Interfejs](iclrgcmanager-interface.md)
- [Interfejsy hostingu środowiska CLR](clr-hosting-interfaces.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
- [Hosting](index.md)
