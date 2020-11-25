---
title: ICLRMetaHost::EnumerateLoadedRuntimes — Metoda
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
ms.openlocfilehash: 98184dd6ea16df066905039b028acd689ff3f290
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730438"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a>ICLRMetaHost::EnumerateLoadedRuntimes — Metoda

Zwraca Wyliczenie, które zawiera prawidłowy wskaźnik interfejsu [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) dla każdej wersji środowiska uruchomieniowego języka wspólnego (CLR), który jest ładowany w danym procesie. Ta metoda zastępuje funkcję [GetVersionFromProcess —](getversionfromprocess-function.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `hndProcess`  
 podczas Dojście procesu do sprawdzenia pod kątem załadowanych środowiska uruchomieniowego.  
  
 `ppEnumerator`  
 określoną <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> Wyliczenie interfejsów [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) odpowiadających każdemu CLR, który jest ładowany przez proces.  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Metoda została ukończona pomyślnie.|  
|E_POINTER|`ppEnumerator` ma wartość null.|  
  
## <a name="remarks"></a>Uwagi  

 Ta metoda zawiera wszystkie załadowane środowiska uruchomieniowe, nawet jeśli zostały załadowane przy użyciu przestarzałych funkcji, takich jak [CorBindToRuntime](corbindtoruntime-function.md).  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Obiekt ServiceHost. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRMetaHost — Interfejs](iclrmetahost-interface.md)
- [Hosting](index.md)
