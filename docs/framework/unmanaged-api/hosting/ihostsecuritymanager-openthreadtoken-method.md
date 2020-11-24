---
title: IHostSecurityManager::OpenThreadToken — Metoda
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
ms.openlocfilehash: 30ec8cc8bbbd6d49f89cd67371c3326c0cb0df9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680615"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>IHostSecurityManager::OpenThreadToken — Metoda

Otwiera token dostępu swobodnego skojarzony z aktualnie wykonywanym wątkiem.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,
    [in]  BOOL     bOpenAsSelf,
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `dwDesiredAccess`  
 podczas Maska wartości dostępu określająca żądane typy dostępu do tokenu wątku. Te wartości są zdefiniowane w funkcji Win32 `OpenThreadToken` . Żądane typy dostępu są uzgadniane z poufną listą kontroli dostępu (DACL) tokenu, aby określić, które typy dostępu mają być udzielone lub odrzucane.  
  
 `bOpenAsSelf`  
 [w] `true` Aby określić, że sprawdzanie dostępu należy przeprowadzić przy użyciu kontekstu zabezpieczeń procesu dla wątku wywołującego; `false` Aby określić, że sprawdzanie dostępu ma być wykonywane przy użyciu kontekstu zabezpieczeń dla samego wątku wywołującego. Jeśli wątek personifikuje klienta, kontekst zabezpieczeń może być procesem klienta.  
  
 `phThreadToken`  
 określoną Wskaźnik do nowo otwartego tokenu dostępu.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken` pomyślnie zwrócono.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Uwagi  

 `IHostSecurityManager::OpenThreadToken` zachowuje się podobnie do odpowiedniej funkcji Win32 o tej samej nazwie, z tą różnicą, że funkcja Win32 zezwala obiektowi wywołującemu na przekazywanie dojścia do dowolnego wątku, podczas gdy `IHostSecurityManager::OpenThreadToken` otwiera tylko token skojarzony z wątkiem wywołującym.  
  
 `HANDLE`Typ nie jest zgodny z modelem COM, oznacza to, że jego rozmiar jest specyficzny dla systemu operacyjnego i wymaga organizowania niestandardowego. W ten sposób token jest używany tylko w ramach procesu, między środowiskiem CLR a hostem.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IHostSecurityContext — Interfejs](ihostsecuritycontext-interface.md)
- [IHostSecurityManager — Interfejs](ihostsecuritymanager-interface.md)
