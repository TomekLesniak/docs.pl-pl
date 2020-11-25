---
title: GetAssemblyIdentityFromFile — Funkcja
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
ms.openlocfilehash: 9580dd3bc5a7279549e8deadac95d35a33da74f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724484"
---
# <a name="getassemblyidentityfromfile-function"></a>GetAssemblyIdentityFromFile — Funkcja

Pobiera wskaźnik do `IUnknown` obiektu z określonym `IID` w zestawie w określonej ścieżce pliku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a>Parametry  

 `pwzFilePath`  
 podczas Prawidłowa ścieżka do żądanego zestawu.  
  
 `riid`  
 podczas `IID` Interfejs do zwrócenia.  
  
 `ppIdentity`  
 określoną Zwrócony wskaźnik interfejsu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [IUnknown](/cpp/atl/iunknown)
- [Łączenie statycznych funkcji globalnych](fusion-global-static-functions.md)
