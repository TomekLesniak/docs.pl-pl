---
title: ICLRErrorReportingManager::BeginCustomDump — Metoda
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
ms.openlocfilehash: 199c130d70cfbf0d383c2e0dc148ffe3dc1242d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673566"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a>ICLRErrorReportingManager::BeginCustomDump — Metoda

Określa konfigurację niestandardowych zrzutów sterty dla raportowania błędów.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `dwFlavor`  
 podczas Wartość [ECustomDumpFlavor —](ecustomdumpflavor-enumeration.md) , która wskazuje rodzaj zrzutu sterty, na którym ma zostać skompilowany zrzut sterty niestandardowej.  
  
 `dwNumItems`  
 podczas Długość `items` tablicy. Jeśli `dwFlavor` nie jest DUMP_FLAVOR_Mini, `dwNumItems` powinna być równa zero.  
  
 `items`  
 podczas Tablica wystąpień [CustomDumpItem —](customdumpitem-structure.md) , określająca elementy, które mają zostać dodane do mini zrzutu. Jeśli `dwFlavor` nie jest DUMP_FLAVOR_Mini, `items` powinna mieć wartość null.  
  
 `dwReserved`  
 podczas Zarezerwowane do użytku w przyszłości.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Metoda została pomyślnie zwrócona.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko uruchomieniowe języka wspólnego (CLR) nie zostało załadowane do procesu lub środowisko CLR znajduje się w stanie, w którym nie można uruchomić kodu zarządzanego lub przetworzyć wywołania pomyślnie.|  
|HOST_E_TIMEOUT|Upłynął limit czasu połączenia.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właocicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas oczekiwania na niego zablokowanego wątku lub włókna.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Po powrocie metody E_FAIL nie będzie można używać środowiska CLR w procesie. Kolejne wywołania metod hostingu zwracają HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Uwagi  

 `BeginCustomDump`Metoda ustawia niestandardową konfigurację zrzutu sterty. Metoda [EndCustomDump —](iclrerrorreportingmanager-endcustomdump-method.md) czyści konfigurację zrzutu sterty niestandardowej i zwalnia wszystkie skojarzone Stany. Powinien być wywoływany po zakończeniu niestandardowego zrzutu sterty.  
  
> [!IMPORTANT]
> Niepowodzenie wywołania `EndCustomDump` powoduje przeciek pamięci.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [CustomDumpItem — Struktura](customdumpitem-structure.md)
- [ECustomDumpFlavor — Wyliczenie](ecustomdumpflavor-enumeration.md)
- [ICLRErrorReportingManager — Interfejs](iclrerrorreportingmanager-interface.md)
