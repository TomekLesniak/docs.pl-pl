---
title: ICorRuntimeHost::CreateDomainSetup — Metoda
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
ms.openlocfilehash: 1be7eee5c2591f26c33572446080a4fa4b3b929d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723899"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a>ICorRuntimeHost::CreateDomainSetup — Metoda

Pobiera wskaźnik interfejsu typu IAppDomainSetup — do <xref:System.AppDomainSetup?displayProperty=nameWithType> wystąpienia. `IAppDomainSetup` zapewnia metody konfigurowania aspektów domeny aplikacji przed jej utworzeniem.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pAppDomainSetup`  
 określoną Wskaźnik interfejsu do <xref:System.AppDomainSetup?displayProperty=nameWithType> wystąpienia. Ten parametr jest wpisywany jako `IUnknown` , dlatego obiekty wywołujące powinny na ogół wywołać `QueryInterface` ten wskaźnik, aby uzyskać wskaźnik interfejsu typu `IAppDomainSetup` .  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Operacja zakończyła się pomyślnie.|  
|S_FALSE|Nie można ukończyć operacji.|  
|E_FAIL|Wystąpił nieznany, Katastrofalny błąd. Jeśli metoda zwraca E_FAIL, środowisko uruchomieniowe języka wspólnego (CLR) nie jest już możliwe do użycia w procesie. Kolejne wywołania interfejsów API hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
  
## <a name="remarks"></a>Uwagi  

 Wskaźnik zwrócony z tej metody jest zwykle przekazana jako parametr do metody [CreateDomainEx —](icorruntimehost-createdomainex-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **Wersja .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Zobacz także

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [ICorRuntimeHost — Interfejs](icorruntimehost-interface.md)
