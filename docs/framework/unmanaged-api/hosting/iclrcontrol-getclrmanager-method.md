---
title: ICLRControl::GetCLRManager — Metoda
ms.date: 03/30/2017
api_name:
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
ms.openlocfilehash: d18b3a5c06ac0d3a86f7823f3b140c76c6c9a746
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728358"
---
# <a name="iclrcontrolgetclrmanager-method"></a>ICLRControl::GetCLRManager — Metoda

Pobiera wskaźnik interfejsu do wystąpienia dowolnego z typów Menedżera, który może być używany przez hosta do konfigurowania środowiska uruchomieniowego języka wspólnego (CLR).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `riid`  
 podczas `IID` Typ Menedżera do zwrócenia. `IID`Obsługiwane są następujące wartości.  
  
- IID_ICLRDebugManager: określa, że `ppObject` będzie typu [ICLRDebugManager](iclrdebugmanager-interface.md).  
  
- IID_ICLRErrorReportingManager: określa, że `ppObject` będzie typu [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md).  
  
- IID_ICLRGCManager: określa, że `ppObject` będzie typu [ICLRGCManager](iclrgcmanager-interface.md).  
  
- IID_ICLRHostProtectionManager: określa, że `ppObject` będzie typu [ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md).  
  
- IID_ICLROnEventManager: określa, że `ppObject` będzie typu [ICLROnEventManager](iclroneventmanager-interface.md).  
  
- IID_ICLRPolicyManager: określa, że `ppObject` będzie typu [ICLRPolicyManager](iclrpolicymanager-interface.md).  
  
- IID_ICLRTaskManager: określa, że `ppObject` będzie typu [ICLRTaskManager](iclrtaskmanager-interface.md).  
  
 `ppObject`  
 określoną Wskaźnik interfejsu do żądanego Menedżera lub wartość null, jeśli zażądano nieprawidłowego typu Menedżera.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Metoda została pomyślnie zwrócona.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
|E_NOINTERFACE|Typ interfejsu nie jest obsługiwany.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRControl — Interfejs](iclrcontrol-interface.md)
- [IHostControl — Interfejs](ihostcontrol-interface.md)
