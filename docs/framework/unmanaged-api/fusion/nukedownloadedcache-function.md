---
title: NukeDownloadedCache — Funkcja
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
ms.openlocfilehash: 5ae0a887d666a150b717d495848c8a411d030a09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728579"
---
# <a name="nukedownloadedcache-function"></a>NukeDownloadedCache — Funkcja

Usuwa pamięć podręczną pobierania środowiska uruchomieniowego języka wspólnego (CLR).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca standardowe kody błędów COM, zgodnie z definicją w WinError. h.  
  
## <a name="remarks"></a>Uwagi  

 Pamięć podręczna pobierania środowiska CLR to obszar, w którym zestawy o silnych nazwach pobrane z adresu URL są przechowywane do ponownego użycia.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion. h  
  
 **Biblioteka:** Fusion.dll i Mscorwks.dll. Użyj Fusion.dll zamiast Mscorwks.dll, aby upewnić się, że docelowa jest poprawna wersja .NET Framework.  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [CreateHistoryReader — Funkcja](createhistoryreader-function.md)
- [GetHistoryFileDirectory — Funkcja](gethistoryfiledirectory-function.md)
- [Łączenie statycznych funkcji globalnych](fusion-global-static-functions.md)
