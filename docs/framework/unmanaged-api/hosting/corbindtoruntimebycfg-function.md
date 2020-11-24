---
title: CorBindToRuntimeByCfg — Funkcja
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
ms.openlocfilehash: d319382b577844a804c3e4562676491a15de5f63
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673790"
---
# <a name="corbindtoruntimebycfg-function"></a>CorBindToRuntimeByCfg — Funkcja

Ładuje środowisko uruchomieniowe języka wspólnego (CLR) do procesu przy użyciu informacji o wersji, które są odczytywane z pliku XML.  
  
 Ta funkcja jest przestarzała w .NET Framework 4.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pCfgStream`  
 podczas Wskaźnik do `IStream` obiektu, który odczytuje plik XML.  
  
 `reserved`  
 podczas Zarezerwowane do użytku w przyszłości. Użyj 0 (zero) jako wartości.  
  
 `startupFlags`  
 podczas Wartość wyliczenia [STARTUP_FLAGS](startup-flags-enumeration.md) , która określa zachowanie uruchamiania środowiska CLR.  
  
 `rclsid`  
 podczas `CLSID` Klasy coclass implementującej interfejs [ICorRuntimeHost](icorruntimehost-interface.md) lub [ICLRRuntimeHost](iclrruntimehost-interface.md) . Obsługiwane wartości to CLSID_CorRuntimeHost lub CLSID_CLRRuntimeHost.  
  
 `riid`  
 podczas `IID` `ICorRuntimeHost` `ICLRRuntimeHost` Interfejs lub. Obsługiwane wartości to IID_ICorRuntimeHost lub IID_ICLRRuntimeHost.  
  
 `ppv`  
 określoną Wskaźnik do adresu zwracanego interfejsu.  
  
## <a name="remarks"></a>Uwagi  

 Format pliku XML jest modelowany po standardowym pliku konfiguracji aplikacji. Aby uzyskać więcej informacji na temat plików XML, zobacz [Schemat pliku konfiguracji](../../configure-apps/file-schema/index.md).  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [CorBindToCurrentRuntime — Funkcja](corbindtocurrentruntime-function.md)
- [CorBindToRuntime — Funkcja](corbindtoruntime-function.md)
- [CorBindToRuntimeEx — Funkcja](corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost — Funkcja](corbindtoruntimehost-function.md)
- [ICorRuntimeHost — Interfejs](icorruntimehost-interface.md)
- [Przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md)
