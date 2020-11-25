---
title: ICLRRuntimeInfo::SetDefaultStartupFlags — Metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
ms.openlocfilehash: 8020db491c3b66be38a9f6cbcb7551721859dcd5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723119"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a>ICLRRuntimeInfo::SetDefaultStartupFlags — Metoda

Ustawia flagi uruchamiania i plik konfiguracji hosta, który zostanie użyty do uruchomienia środowiska uruchomieniowego. Ta metoda zastępuje użycie `startupFlags` parametru w funkcjach [CorBindToRuntimeEx](corbindtoruntimeex-function.md) i [CorBindToRuntimeHost —](corbindtoruntimehost-function.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a>Parametry  

 `dwStartupFlags`  
 podczas Flagi uruchamiania hosta do ustawienia. Użyj tych samych flag co w przypadku funkcji [CorBindToRuntimeEx](corbindtoruntimeex-function.md) i [CorBindToRuntimeHost —](corbindtoruntimehost-function.md) .  
  
 `pwzHostConfigFile`  
 podczas Ścieżka katalogu pliku konfiguracji hosta do ustawienia.  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca następujące określone wartości HRESULT, a także błędy HRESULT wskazujące niepowodzenie metody.  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Metoda została ukończona pomyślnie.|  
  
## <a name="remarks"></a>Uwagi  

 Host wielowątkowy powinien synchronizować wywołania z tą metodą. W przeciwnym razie wątek A może wywoływać `SetStartupFlags` metodę po zakończeniu wątku b zakończy wywołanie do `SetStartupFlags` i zanim wątek b uruchomi środowisko uruchomieniowe.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Obiekt ServiceHost. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRRuntimeInfo — Interfejs](iclrruntimeinfo-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
- [Hosting](index.md)
