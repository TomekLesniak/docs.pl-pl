---
title: IHostSecurityManager::SetSecurityContext — Metoda
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
ms.openlocfilehash: dadacaea2b8741afc7b8c51404e2604dc759a629
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680381"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a>IHostSecurityManager::SetSecurityContext — Metoda

Ustawia kontekst zabezpieczeń aktualnie wykonywanego wątku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `eContextType`  
 podczas Jedna z wartości [EContextType —](econtexttype-enumeration.md) , wskazująca, jakiego typu kontekstu środowisko uruchomieniowe języka wspólnego (CLR) umieszcza na hoście.  
  
 `ppSecurityContext`  
 określoną Wskaźnik do adresu nowego obiektu [IHostSecurityContext](ihostsecuritycontext-interface.md) .  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`SetSecurityContext` pomyślnie zwrócono.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Uwagi  

 Środowisko CLR wywołuje `SetSecurityContext` kilka scenariuszy. Przed wykonaniem konstruktorów klas i modułów oraz finalizatorów, środowisko CLR wywołuje `SetSecurityContext` w celu ochrony hosta przed błędami wykonania. Następnie resetuje kontekst zabezpieczeń do oryginalnego stanu po wykonaniu konstruktora lub finalizatora przy użyciu innego wywołania do `SetSecurityContext` . Podobny wzorzec występuje po zakończeniu operacji we/wy. Jeśli Host implementuje [IHostIoCompletionManager](ihostiocompletionmanager-interface.md), środowisko CLR wywołuje się `SetSecurityContext` po wywołaniach hosta [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md).  
  
 W przypadku asynchronicznych punktów w wątkach roboczych, środowisko CLR wywołuje `SetSecurityContext` wewnątrz <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> lub w [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), w zależności od tego, czy host lub środowisko CLR implementuje pulę wątków.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [EContextType — Wyliczenie](econtexttype-enumeration.md)
- [ICLRIoCompletionManager — Interfejs](iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager — Interfejs](ihostiocompletionmanager-interface.md)
- [IHostSecurityContext — Interfejs](ihostsecuritycontext-interface.md)
- [IHostSecurityManager — Interfejs](ihostsecuritymanager-interface.md)
- [IHostThreadPoolManager — Interfejs](ihostthreadpoolmanager-interface.md)
