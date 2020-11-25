---
title: ICorRuntimeHost::CreateDomain — Metoda
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
ms.openlocfilehash: c495ce47b699d2e32d1f02e4afcf0444a9930c34
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723912"
---
# <a name="icorruntimehostcreatedomain-method"></a>ICorRuntimeHost::CreateDomain — Metoda

Tworzy domenę aplikacji. Obiekt wywołujący otrzymuje wskaźnik interfejsu typu <xref:System._AppDomain> do wystąpienia typu <xref:System.AppDomain?displayProperty=nameWithType> .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pwzFriendlyName`  
 podczas Opcjonalny parametr używany do nadawania przyjaznej nazwy do domeny. Ta przyjazna nazwa może być wyświetlana w interfejsach użytkownika, takich jak debugery, aby identyfikować domenę.  
  
 `pIdentityArray`  
 podczas Opcjonalna tablica wskaźników do `IIdentity` wystąpień, które reprezentują dowody mapowane za pomocą zasad zabezpieczeń w celu ustanowienia zestawu uprawnień. `IIdentity`Obiekt można uzyskać przez wywołanie metody. [CreateEvidence](icorruntimehost-createevidence-method.md)  
  
 `pAppDomain`  
 określoną Wskaźnik interfejsu typu <xref:System._AppDomain> do wystąpienia <xref:System.AppDomain?displayProperty=nameWithType> , które może służyć do dalszej kontroli nad domeną.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Operacja zakończyła się pomyślnie.|  
|S_FALSE|Nie można ukończyć operacji.|  
|E_FAIL|Wystąpił nieznany, Katastrofalny błąd. Jeśli metoda zwraca E_FAIL, środowisko uruchomieniowe języka wspólnego (CLR) nie jest już możliwe do użycia w procesie. Kolejne wywołania interfejsów API hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko CLR nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:** 1,0, 1,1  
  
## <a name="see-also"></a>Zobacz także

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [ICorRuntimeHost — Interfejs](icorruntimehost-interface.md)
