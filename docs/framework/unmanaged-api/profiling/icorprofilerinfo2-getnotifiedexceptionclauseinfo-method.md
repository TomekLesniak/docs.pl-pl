---
title: ICorProfilerInfo2::GetNotifiedExceptionClauseInfo — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetNotifiedExceptionClauseInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
- GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
ms.assetid: f9594a7e-cb0c-4c48-accb-29f762aa0c21
topic_type:
- apiref
ms.openlocfilehash: b0d94f5004da85caf0460e8f1d1b2d964944b045
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727071"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>ICorProfilerInfo2::GetNotifiedExceptionClauseInfo — Metoda

Pobiera natywne informacje o adresie i ramce dla klauzuli wyjątku ( `catch` / `finally` / `filter` ), która ma zostać uruchomiona lub właśnie została uruchomiona.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a>Parametry  

 `pinfo`  
 określoną Wskaźnik do struktury [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) , który opisuje bieżące wystąpienie klauzuli wyjątku i skojarzoną z nią ramkę.  
  
## <a name="remarks"></a>Uwagi  

 Po otrzymaniu powiadomienia o wyjątku `GetNotifiedExceptionClauseInfo` może służyć do uzyskania natywnego adresu i informacji o ramce dla klauzuli wyjątku ( `catch` / `finally` / `filter` ), która ma zostać uruchomiona ([ICorProfilerCallback:: ExceptionCatcherEnter —](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyEnter —](icorprofilercallback-exceptionunwindfinallyenter-method.md)lub [ICorProfilerCallback:: ExceptionSearchFilterEnter —](icorprofilercallback-exceptionsearchfilterenter-method.md) wywołanie zwrotne jest odbierane przez Profiler) lub zostało właśnie uruchomione ([ICorProfilerCallback:: ExceptionCatcherLeave —](icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyLeave —](icorprofilercallback-exceptionunwindfinallyleave-method.md)lub [ICorProfilerCallback:: ExceptionSearchFilterLeave —](icorprofilercallback-exceptionsearchfilterleave-method.md) wywołanie zwrotne jest odbierane przez Profiler).  
  
 To wywołanie można wykonać w dowolnym momencie po odebraniu jednego z wywołań zwrotnych powyżej do momentu otrzymania zgodnego wywołania zwrotnego urlopu lub wyjątek zagnieżdżony w bieżącej klauzuli, w takim przypadku nie ma powiadomienia o opuszczeniu dla tej klauzuli. Należy zauważyć, że nie jest to możliwe w przypadku zgłoszonego wyjątku do ucieczki `filter` klauzuli wyjątku, więc w takim przypadku zawsze istnieje powiadomienie o pozostawieniu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo — Interfejs](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 — Interfejs](icorprofilerinfo2-interface.md)
