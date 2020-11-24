---
title: ICLRGCManager::SetGCStartupLimits — Metoda
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
ms.openlocfilehash: 169d344975762b97f89e8dc32d72f2b9c95fea11
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678184"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a>ICLRGCManager::SetGCStartupLimits — Metoda

Ustawia rozmiar segmentu wyrzucania elementów bezużytecznych i maksymalny rozmiar generacji 0 systemu odzyskiwania pamięci.  
  
> [!IMPORTANT]
> Począwszy od .NET Framework 4,5, można ustawić rozmiar segmentu i rozmiar maksymalnej generacji 0 na wartości większe niż przy `DWORD` użyciu metody [ICLRGCManager2:: SetGCStartupLimitsEx —](iclrgcmanager2-setgcstartuplimitsex-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `SegmentSize`  
 podczas Określony rozmiar segmentu odzyskiwania pamięci.  
  
 Minimalny rozmiar segmentu to 4 MB. Segmenty można zwiększyć z przyrostem wynoszącym 1 MB lub większą.  
  
 `MaxGen0Size`  
 podczas Określony maksymalny rozmiar dla generacji 0.  
  
 Minimalna wielkość generacji 0 to 64 KB.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`SetGCStartupLimits` pomyślnie zwrócono.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Uwagi  

 Wartości, które `SetGCStartupLimits` ustawia się, można określić tylko raz. Późniejsze wywołania `SetGCStartupLimits` są ignorowane.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Automatyczne zarządzanie pamięcią](../../../standard/automatic-memory-management.md)
- [Odzyskiwanie pamięci](../../../standard/garbage-collection/index.md)
- [ICLRControl — Interfejs](iclrcontrol-interface.md)
- [ICLRGCManager — Interfejs](iclrgcmanager-interface.md)
