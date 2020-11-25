---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile — Metoda
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
ms.openlocfilehash: 443acfa77dc8103008263f19bed116d02e7ea676
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716745"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a>ICLRAssemblyIdentityManager::GetBindingIdentityFromFile — Metoda

Pobiera dane powiązania tożsamości zestawu z określoną ścieżką do pliku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pwzFilePath`  
 podczas Ścieżka do pliku do oceny.  
  
 `dwFlags`  
 podczas Wartość wyliczenia [ECLRAssemblyIdentityFlags —](eclrassemblyidentityflags-enumeration.md) , która wskazuje typ tożsamości zestawu. Udostępniane do przyszłej rozszerzalności. CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT jest jedyną wartością obsługiwaną przez środowisko uruchomieniowe języka wspólnego (CLR) w wersji 2,0.  
  
 `pwzBuffer`  
 określoną Bufor zawierający dane tożsamości nieprzezroczystego zestawu.  
  
 `pcchBufferSize`  
 [in. out] Wskaźnik do rozmiaru `pwzBuffer` .  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Metoda została pomyślnie zwrócona.|  
|E_INVALIDARG|Podana `pwzFilePath` wartość jest równa null.|  
|ERROR_INSUFFICIENT_BUFFER|Rozmiar `pwzBuffer` jest za mały.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Jeśli metoda zwraca E_FAIL, środowisko CLR nie będzie już można używać w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Uwagi  

 `GetBindingIdentityFromFile` jest zazwyczaj wywoływana dwukrotnie. Pierwsze wywołanie dostarcza wartość null dla `pwzBuffer` , a metoda zwraca odpowiedni rozmiar w `pcchBufferSize` . Drugie wywołanie dostarcza odpowiednio przydzielony bufor, a metoda zwraca z rzeczywistymi danymi buforu po zakończeniu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRAssemblyIdentityManager — Interfejs](iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList — Interfejs](iclrassemblyreferencelist-interface.md)
- [ICLRHostBindingPolicyManager — Interfejs](iclrhostbindingpolicymanager-interface.md)
