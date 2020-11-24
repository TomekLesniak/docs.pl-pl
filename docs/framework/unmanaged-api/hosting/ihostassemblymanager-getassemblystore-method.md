---
title: IHostAssemblyManager::GetAssemblyStore — Metoda
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type:
- apiref
ms.openlocfilehash: 936ea068f3cc5567a00af5f2bdd5f3d9cd52bc81
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681187"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a>IHostAssemblyManager::GetAssemblyStore — Metoda

Pobiera wskaźnik interfejsu do [IHostAssemblyStore](ihostassemblystore-interface.md) , który reprezentuje listę zestawów załadowanych przez hosta.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppAssemblyStore`  
 określoną Wskaźnik funkcji do `IHostAssemblyStore` wystąpienia lub wartość null, Jeśli host nie implementuje `IHostAssemblyStore` .  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`GetAssemblyStore` pomyślnie zwrócono.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
|E_NOINTERFACE|Host nie oferuje implementacji programu `IHostAssemblyStore` .|  
  
## <a name="remarks"></a>Uwagi  

 `IHostAssemblyStore` dostarcza metody, które umożliwiają hostowi powiązanie z zestawami i modułami niezależnie od środowiska CLR. Hosty zwykle zapewniają magazyny zestawów pozwalające ładować zestawy z formatów innych niż system plików.  
  
> [!NOTE]
> Jeśli host nie jest zaimplementowany `IHostAssemblyStore` , `GetAssemblyStore` powinien zwrócić wartość HRESULT o wartości E_NOINTERFACE i powinien mieć ustawioną wartość `ppAssemblyStore` null.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IHostAssemblyManager — Interfejs](ihostassemblymanager-interface.md)
- [IHostAssemblyStore — Interfejs](ihostassemblystore-interface.md)
