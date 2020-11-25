---
title: IHostMemoryManager::VirtualQuery — Metoda
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualQuery
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type:
- apiref
ms.openlocfilehash: 6e3cb5bcec831f143d45f733c9e2f977390aade6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731248"
---
# <a name="ihostmemorymanagervirtualquery-method"></a>IHostMemoryManager::VirtualQuery — Metoda

Służy jako otoka logiczna dla odpowiadającej jej funkcji Win32. Implementacja Win32 `VirtualQuery` Pobiera informacje o zakresie stron w wirtualnej przestrzeni adresowej procesu wywołującego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `lpAddress`  
 podczas Wskaźnik na adres w pamięci wirtualnej, który ma być wysyłany do zapytania.  
  
 `lpBuffer`  
 określoną Wskaźnik do struktury zawierającej informacje o określonym regionie pamięci.  
  
 `dwLength`  
 podczas Rozmiar (w bajtach) bufora, który `lpBuffer` wskazuje.  
  
 `pResult`  
 określoną Wskaźnik do liczby bajtów zwróconych przez bufor informacji.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`VirtualQuery` pomyślnie zwrócono.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Gdy metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Uwagi  

 `VirtualQuery` zawiera informacje o zakresie stron w wirtualnej przestrzeni adresowej procesu wywołującego. Ta implementacja ustawia wartość `pResult` parametru na liczbę bajtów zwracanych w buforze informacji i zwraca wartość HRESULT. W funkcji Win32 `VirtualQuery` wartość zwracana jest rozmiarem buforu. Aby uzyskać więcej informacji, zobacz dokumentację platformy systemu Windows.  
  
> [!IMPORTANT]
> Implementacja systemu operacyjnego nie pociągnie za `VirtualQuery` sobą zakleszczenie i może działać do ukończenia z losowymi wątkami zawieszonymi w kodzie użytkownika. Należy zachować ostrożność podczas implementowania hostowanej wersji tej metody.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IHostMemoryManager — Interfejs](ihostmemorymanager-interface.md)
