---
title: ICorProfilerInfo9, interfejs
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: f38195b1a7983e23c7f5c20055ea8c2a8bfcb7d8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556853"
---
# <a name="icorprofilerinfo9-interface"></a>ICorProfilerInfo9, interfejs

Podklasa elementu [ICorProfilerInfo8](icorprofilerinfo8-interface.md) , która dostarcza metody do wykonywania zapytań o informacje o funkcjach z wieloma natywnymi wersjami kodu.  

## <a name="methods"></a>Metody  

| Metoda|Opis|  
| ------------|-----------------|  
|[GetNativeCodeStartAddresses, metoda](icorprofilerinfo9-getnativecodestartaddresses-method.md)| Mając functionId i rejitId, wylicza natywny adres początkowy kodu dla wszystkich wersji trybie JIT tego kodu, który już istnieje. |
|[GetILToNativeMapping3, metoda](icorprofilerinfo9-getiltonativemapping3-method.md)| Przy podanym adresie początkowym kodu natywnego program zwraca informacje mapowania natywnego do IL dla tej trybie JIT wersji kodu. |
|[GetCodeInfo4, metoda](icorprofilerinfo9-getcodeinfo4-method.md)| Przy podanym adresie początkowym kodu natywnego program zwraca bloki pamięci wirtualnej, która przechowuje ten kod. |

## <a name="requirements"></a>Wymagania  
**Platformy:** Zobacz [obsługiwane systemy operacyjne .NET Core](../../../core/install/windows.md?pivots=os-windows).  
**Nagłówek:** CorProf. idl, CorProf. h  
**Wersje .NET:**[!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]  

## <a name="see-also"></a>Zobacz także

- [Interfejsy profilowania](profiling-interfaces.md)
