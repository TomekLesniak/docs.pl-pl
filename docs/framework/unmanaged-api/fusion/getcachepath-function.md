---
title: GetCachePath — Funkcja
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
ms.openlocfilehash: c22f0701cfda4523f595366a97435ef8da08b0cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724471"
---
# <a name="getcachepath-function"></a>GetCachePath — Funkcja

Pobiera ścieżkę do buforowanego zestawu przy użyciu określonych flag.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a>Parametry  

 `dwCacheFlags`  
 podczas Wartość [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) , która wskazuje Źródło buforowanego zestawu.  
  
 `pwzCachePath`  
 określoną Zwrócony wskaźnik do ścieżki.  
  
 `pcchPath`  
 [in. out] Żądana Maksymalna długość `pwzCachePath` i po powrocie — rzeczywista długość `pwzCachePath` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ASM_CACHE_FLAGS — Wyliczenie](asm-cache-flags-enumeration.md)
- [Łączenie statycznych funkcji globalnych](fusion-global-static-functions.md)
