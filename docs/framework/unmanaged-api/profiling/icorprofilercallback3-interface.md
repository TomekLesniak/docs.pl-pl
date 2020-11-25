---
title: ICorProfilerCallback3 — Interfejs
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
ms.openlocfilehash: fd482bfe8e95a53cafd1530c88f09df146a1b150
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729437"
---
# <a name="icorprofilercallback3-interface"></a>ICorProfilerCallback3 — Interfejs

Zapewnia metody wywołania zwrotnego, które są używane przez środowisko uruchomieniowe języka wspólnego (CLR) do przekazywania informacji o stanie dołączania i odłączania do profilera.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[InitializeForAttach, metoda](icorprofilercallback3-initializeforattach-method.md)|Wywoływane przez środowisko CLR, aby dać profilerowi możliwość zainicjowania stanu po operacji Attach.|  
|[ProfilerAttachComplete, metoda](icorprofilercallback3-profilerattachcomplete-method.md)|Wywoływane przez środowisko CLR, aby wskazać, że profiler może teraz wywoływać metody przechwytywania.|  
|[ProfilerDetachSucceeded, metoda](icorprofilercallback3-profilerdetachsucceeded-method.md)|Powiadamia program profilujący, że aparat plików wykonywalnych języka wspólnego (CLR) ma zwolnić plik DLL profilera.|  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy profilowania](profiling-interfaces.md)
- [ICorProfilerInfo — Interfejs](icorprofilerinfo-interface.md)
- [ICorProfilerCallback2 — Interfejs](icorprofilercallback2-interface.md)
- [ICorProfilerCallback4 — Interfejs](icorprofilercallback4-interface.md)
