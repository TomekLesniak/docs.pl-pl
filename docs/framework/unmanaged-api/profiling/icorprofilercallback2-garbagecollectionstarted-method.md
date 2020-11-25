---
title: ICorProfilerCallback2::GarbageCollectionStarted — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
ms.openlocfilehash: 63a8d212a61bd73f44995f0e057eeff96f9a5554
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731959"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>ICorProfilerCallback2::GarbageCollectionStarted — Metoda

Powiadamia profiler kodu o rozpoczęciu odzyskiwania pamięci.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a>Parametry  

 `cGenerations`  
 podczas Łączna liczba wpisów w `generationCollected` tablicy.  
  
 `generationCollected`  
 podczas Tablica wartości logicznych, które są, `true` Jeśli generacja, która odpowiada indeksowi tablicy jest zbierana przez to wyrzucanie elementów bezużytecznych; w przeciwnym razie `false` .  
  
 Tablica jest indeksowana przez wartość wyliczenia [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) , która wskazuje generowanie.  
  
 `reason`  
 podczas Wartość wyliczenia [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) , która wskazuje przyczynę wyrzucania elementów bezużytecznych.  
  
## <a name="remarks"></a>Uwagi  

 Wszystkie wywołania zwrotne, które odnoszą się do tego wyrzucania elementów bezużytecznych, następują między `GarbageCollectionStarted` wywołaniem zwrotnym a odpowiednim wywołaniem zwrotnym [ICorProfilerCallback2:: GarbageCollectionFinished —](icorprofilercallback2-garbagecollectionfinished-method.md) Te wywołania zwrotne nie muszą występować w tym samym wątku.  
  
 Program profilujący może bezpiecznie zbadać obiekty w ich oryginalnych lokalizacjach podczas `GarbageCollectionStarted` wywołania zwrotnego. Moduł wyrzucania elementów bezużytecznych rozpocznie przesuwanie obiektów po zwrocie z `GarbageCollectionStarted` . Po zwróceniu przez profiler z tego wywołania zwrotnego, profiler powinien wziąć pod uwagę wszystkie identyfikatory obiektów, które mają być nieprawidłowe do momentu odebrania `ICorProfilerCallback2::GarbageCollectionFinished` wywołania zwrotnego.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerCallback — Interfejs](icorprofilercallback-interface.md)
- [ICorProfilerCallback2 — Interfejs](icorprofilercallback2-interface.md)
