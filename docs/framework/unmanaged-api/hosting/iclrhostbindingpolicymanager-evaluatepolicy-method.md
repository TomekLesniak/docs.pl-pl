---
title: ICLRHostBindingPolicyManager::EvaluatePolicy — Metoda
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
ms.openlocfilehash: 9840217abdf8b3e1d0917b7447572b6860c181c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720311"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a>ICLRHostBindingPolicyManager::EvaluatePolicy — Metoda

Oblicza zasady powiązań w imieniu hosta.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pwzReferenceIdentity`  
 podczas Odwołanie do zestawu przed oceną zasad.  
  
 `pbApplicationPolicy`  
 podczas Wskaźnik do buforu, który zawiera dane zasad.  
  
 `cbAppPolicySize`  
 podczas Rozmiar `pbApplicationPolicy` buforu.  
  
 `pwzPostPolicyReferenceIdentity`  
 określoną Odwołanie do zestawu po dokonaniu oceny nowych danych zasad.  
  
 `pcchPostPolicyReferenceIdentity`  
 [in. out] Wskaźnik do rozmiaru buforu odwołań tożsamości zestawu po dokonaniu oceny nowych danych zasad.  
  
 `pdwPoliciesApplied`  
 określoną Wskaźnik do logicznej lub kombinacji wartości [EBindPolicyLevels —](ebindpolicylevels-enumeration.md) wskazujących, które zasady zostały zastosowane.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Ocena została zakończona pomyślnie.|  
|E_INVALIDARG|Albo `pwzReferenceIdentity` `pbApplicationPolicy` jest odwołaniem o wartości null.|  
|ERROR_INSUFFICIENT_BUFFER|`cbAppPolicySize` jest za mała.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Uwagi  

 `EvaluatePolicy`Metoda umożliwia hostowi wpływ na powiązania zasad w celu obsługi wymagań dotyczących wersji zestawu specyficznych dla hosta. Sam aparat zasad pozostaje wewnątrz środowiska CLR.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRHostBindingPolicyManager — Interfejs](iclrhostbindingpolicymanager-interface.md)
