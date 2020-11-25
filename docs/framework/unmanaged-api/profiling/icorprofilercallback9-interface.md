---
title: ICorProfilerCallback9, interfejs
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 23b91a2a58c6e76b31b94e0fa3661dfbc8e18e33
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712771"
---
# <a name="icorprofilercallback9-interface"></a>ICorProfilerCallback9, interfejs

[Obsługiwane w .NET Framework 4.7.2 i nowszych wersjach]  

 Podklasa elementu [ICorProfilerCallback8](icorprofilercallback8-interface.md) , która zapewnia metodę wywołania zwrotnego używaną przez środowisko uruchomieniowe języka wspólnego do powiadomienia profilera, że metoda dynamiczna została odtworzona, a następnie zwolniona z pamięci.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[DynamicMethodUnloaded, metoda](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|Powiadamia program profilujący, że metoda dynamiczna została odtworzona, a następnie zwolniona.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
**.NET Framework wersje:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Zobacz także

- [Interfejsy profilowania](profiling-interfaces.md)
- [ICorProfilerCallback8, interfejs](icorprofilercallback9-interface.md)
- [ICorProfilerCallback8. DynamicMethodJITCompilationStarted — Metoda](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8. DynamicMethodJITCompilationFinished — Metoda](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
