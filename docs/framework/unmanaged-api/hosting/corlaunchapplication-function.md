---
title: CorLaunchApplication — Funkcja
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
ms.openlocfilehash: ca427439f03d92b20e7714b9724d90b240e9cecb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704074"
---
# <a name="corlaunchapplication-function"></a>CorLaunchApplication — Funkcja

Uruchamia aplikację pod określoną ścieżką sieciową przy użyciu określonych manifestów i innych danych aplikacji.  
  
 Ta funkcja jest przestarzała w .NET Framework 4.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `dwClickOnceHost`  
 podczas Wartość wyliczenia [HOST_TYPE](host-type-enumeration.md) , która określa typ hosta, który uruchamia aplikację.  
  
 `pwzAppFullName`  
 podczas Pełna nazwa aplikacji, która jest uruchamiana.  
  
 `dwManifestPaths`  
 podczas Liczba ścieżek manifestu dla aplikacji.  
  
 `ppwzManifestPaths`  
 podczas Tablica ciągów, z których każdy określa ścieżkę do manifestu dla aplikacji, która jest uruchamiana.  
  
 `dwActivationData`  
 podczas Liczba elementów danych aktywacji dla aplikacji, która jest uruchamiana.  
  
 `ppwzActivationData`  
 podczas Tablica ciągów, z których każdy jest elementem danych aktywacji dla aplikacji, która jest uruchamiana.  
  
 `lpProcessInformation`  
 określoną Wskaźnik do informacji o procesie, w którym aplikacja została załadowana.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE. h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Przestarzałe funkcje hostingu środowiska CLR](deprecated-clr-hosting-functions.md)
