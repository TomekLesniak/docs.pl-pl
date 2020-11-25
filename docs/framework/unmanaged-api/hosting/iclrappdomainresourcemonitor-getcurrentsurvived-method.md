---
title: ICLRAppDomainResourceMonitor::GetCurrentSurvived — Metoda
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
ms.openlocfilehash: eba9caece91e369cd46aed652b559ace49c77725
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704910"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>ICLRAppDomainResourceMonitor::GetCurrentSurvived — Metoda

Pobiera liczbę bajtów, które przeżyły ostatnią pełną, blokującą wyrzucanie elementów bezużytecznych i przywoływanych przez bieżącą domenę aplikacji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a>Parametry  

 `dwAppDomainId`  
 podczas Identyfikator żądanej domeny aplikacji.  
  
 `pAppDomainBytesSurvived`  
 określoną Wskaźnik do liczby bajtów przeprowadzonych po ostatnim wyrzucaniu elementów bezużytecznych przechowywanych przez tę domenę aplikacji. Po pełnej kolekcji ta liczba jest dokładna i kompletna. Po zakończeniu zbierania danych tymczasowych ten numer jest potencjalnie niekompletny. Ten parametr może być `null` .  
  
 `pRuntimeBytesSurvived`  
 określoną Wskaźnik do łącznej liczby bajtów przeczytanych z ostatniego wyrzucania elementów bezużytecznych. Po pełnej kolekcji ta liczba reprezentuje liczbę bajtów przechowywanych w stertach zarządzanych. Po zbiorze tymczasowych ta liczba reprezentuje liczbę bajtów przechowywanych na żywo w generacjach tymczasowych. Ten parametr może być `null` .  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Metoda została ukończona pomyślnie.|  
|COR_E_APPDOMAINUNLOADED|Domena aplikacji została zwolniona lub nie istnieje.|  
  
## <a name="remarks"></a>Uwagi  

 Statystyki są aktualizowane tylko po pełnej, blokującej wyrzucaniu elementów bezużytecznych; oznacza to, że kolekcja obejmująca wszystkie generacje i która zatrzyma aplikację podczas zbierania. Na przykład <xref:System.GC.Collect?displayProperty=nameWithType> Przeciążenie metody wykonuje pełną, blokującą kolekcję. Współbieżne wyrzucanie elementów bezużytecznych odbywa się w tle i nie blokuje aplikacji.  
  
 `GetCurrentSurvived`Metoda jest niezarządzanym odpowiednikiem właściwości zarządzanej <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Obiekt ServiceHost. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRAppDomainResourceMonitor — Interfejs](iclrappdomainresourcemonitor-interface.md)
- [Monitorowanie zasobów domeny aplikacji](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
- [Hosting](index.md)
