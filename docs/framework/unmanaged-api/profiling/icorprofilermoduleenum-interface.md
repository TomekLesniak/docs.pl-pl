---
title: ICorProfilerModuleEnum — Interfejs
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum
helpviewer_keywords:
- ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type:
- apiref
ms.openlocfilehash: 98b64289b7d512c4e73cf4d40e89319532c6704a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722820"
---
# <a name="icorprofilermoduleenum-interface"></a>ICorProfilerModuleEnum — Interfejs

Dostarcza metody sekwencyjnie iteracji przez kolekcję modułów ładowanych przez aplikację lub profiler.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Clone — Metoda](icorprofilermoduleenum-clone-method.md)|Pobiera wskaźnik interfejsu do kopii tego `ICorProfilerModuleEnum` interfejsu.|  
|[GetCount, metoda](icorprofilermoduleenum-getcount-method.md)|Pobiera liczbę modułów zarządzanych, które zostały załadowane do aplikacji.|  
|[Next, metoda](icorprofilermoduleenum-next-method.md)|Pobiera określoną liczbę modułów ciągłego z kolekcji sekwencyjnej obiektów, rozpoczynając od bieżącej pozycji modułu wyliczającego w sekwencji.|  
|[Reset — Metoda](icorprofilermoduleenum-reset-method.md)|Przenosi kursor modułu wyliczającego do początkowego położenia sekwencji.|  
|[Skip — Metoda](icorprofilermoduleenum-skip-method.md)|Przesuwa pozycję kursora modułu wyliczającego tak, aby określona liczba elementów została pominięta.|  
  
## <a name="remarks"></a>Uwagi  

 `ICorProfilerModuleEnum`Interfejs jest modułem wyliczającym. Umożliwia odbiorcom tablicy ściąganie elementów od nadawcy według stawki, która jest odpowiednia dla odbiornika. Innymi słowy, odbiorca może jawnie kontrolować przepływ elementów tablicy, co pozwala uniknąć problemów związanych z przekazywaniem dużych tablic jako parametrów metody.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo — Interfejs](icorprofilerinfo-interface.md)
- [Interfejsy profilowania](profiling-interfaces.md)
- [EnumModules, metoda](icorprofilerinfo3-enummodules-method.md)
