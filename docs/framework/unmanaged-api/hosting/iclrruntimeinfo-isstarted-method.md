---
title: ICLRRuntimeInfo::IsStarted — Metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
ms.openlocfilehash: 1dfeb6101a6b8e33ab2fe35f318087d7f1834b6a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714890"
---
# <a name="iclrruntimeinfoisstarted-method"></a>ICLRRuntimeInfo::IsStarted — Metoda

Wskazuje, czy środowisko uruchomieniowe zostało uruchomione (czyli czy [Metoda ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) została wywołana i została zakończona pomyślnie).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a>Parametry  

 `pbStarted`  
 [out] `true` w przypadku uruchomienia tego środowiska uruchomieniowego; w przeciwnym razie `false` .  
  
 `pdwStartupFlags`  
 określoną Zwraca flagi, które zostały użyte do uruchomienia środowiska uruchomieniowego.  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Metoda została ukończona pomyślnie.|  
|E_NOTIMPL|Wersja środowiska uruchomieniowego języka wspólnego (CLR) jest wcześniejsza niż wersja środowiska CLR w .NET Framework 4.|  
  
## <a name="remarks"></a>Uwagi  

 Ta metoda nie działa w przypadku wersji CLR wcześniejszych niż wersja środowiska CLR w .NET Framework 4.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Obiekt ServiceHost. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRRuntimeInfo — Interfejs](iclrruntimeinfo-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
- [Hosting](index.md)
