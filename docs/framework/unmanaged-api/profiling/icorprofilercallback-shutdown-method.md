---
title: ICorProfilerCallback::Shutdown — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
ms.openlocfilehash: 9761eb5085a77279c4d07d39946a5ad1453ecaaf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717270"
---
# <a name="icorprofilercallbackshutdown-method"></a>ICorProfilerCallback::Shutdown — Metoda

Powiadamia program profilujący, że aplikacja jest zamykana.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Uwagi  

 Kod profilera nie może bezpiecznie wywołać metod interfejsu [ICorProfilerInfo](icorprofilerinfo-interface.md) po `Shutdown` wywołaniu metody. Wszystkie wywołania `ICorProfilerInfo` metod powodują niezdefiniowane zachowanie po `Shutdown` powrocie metody. Po zamknięciu mogą nadal występować pewne niezmienne zdarzenia. Profiler powinien zwrócić uwagę natychmiast po wystąpieniu tego problemu.  
  
 `Shutdown`Metoda zostanie wywołana tylko wtedy, gdy zarządzana aplikacja, która jest profilowana, została uruchomiona jako kod zarządzany (oznacza to, że początkowa ramka na stosie procesów jest zarządzana). Jeśli aplikacja została uruchomiona jako kod niezarządzany, ale później przeskoczy do kodu zarządzanego, tworząc wystąpienie środowiska uruchomieniowego języka wspólnego (CLR), wówczas `Shutdown` nie zostanie wywołane. W takich przypadkach Profiler powinien zawierać w swojej bibliotece `DllMain` procedurę, która używa wartości DLL_PROCESS_DETACH do zwolnienia wszelkich zasobów i przeprowadzania czyszczenia danych, takich jak opróżnianie śladów na dysk i tak dalej.  
  
 Ogólnie rzecz biorąc, profiler musi poradzić sobie z nieoczekiwanymi zamknięciami. Na przykład proces może być zatrzymany przez `TerminateProcess` metodę Win32's (zadeklarowany w Winbase. h). W innych przypadkach środowisko CLR zatrzyma pewne zarządzane wątki (wątki w tle) bez dostarczania do nich uporządkowanych komunikatów o zniszczeniu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerCallback — Interfejs](icorprofilercallback-interface.md)
- [Initialize — Metoda](icorprofilercallback-initialize-method.md)
