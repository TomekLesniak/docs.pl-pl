---
title: ICorProfilerObjectEnum — Interfejs
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum
helpviewer_keywords:
- ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 13e1651c-9523-40ef-bfd7-87fb94519f8b
topic_type:
- apiref
ms.openlocfilehash: 73c9f07ff9a7bffc2fb01c0dde390ca8364500b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731179"
---
# <a name="icorprofilerobjectenum-interface"></a>ICorProfilerObjectEnum — Interfejs

Zapewnia metody sekwencyjnej iteracji przez kolekcję zablokowanych obiektów, które są generowane przez [Ngen.exe (Generator obrazu natywnego)](../../tools/ngen-exe-native-image-generator.md).  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Clone — Metoda](icorprofilerobjectenum-clone-method.md)|Pobiera wskaźnik interfejsu do kopii tego `ICorProfilerObjectEnum` interfejsu.|  
|[GetCount, metoda](icorprofilerobjectenum-getcount-method.md)|Pobiera łączną liczbę zablokowanych obiektów w kolekcji.|  
|[Next, metoda](icorprofilerobjectenum-next-method.md)|Pobiera określoną liczbę obiektów ciągłego z kolekcji sekwencyjnej obiektów, rozpoczynając od bieżącej pozycji modułu wyliczającego w sekwencji.|  
|[Reset — Metoda](icorprofilerobjectenum-reset-method.md)|Przenosi ten wskaźnik modułu wyliczającego do początkowego położenia sekwencji.|  
|[Skip — Metoda](icorprofilerobjectenum-skip-method.md)|Przesuwa kursor tego modułu wyliczającego z jego bieżącej pozycji, tak aby określona liczba elementów została pominięta.|  
  
## <a name="remarks"></a>Uwagi  

 `ICorProfilerObjectEnum`Interfejs jest modułem wyliczającym. Umożliwia odbiorcom tablicy ściąganie elementów od nadawcy według stawki, która jest odpowiednia dla odbiornika. Innymi słowy, odbiorca może jawnie kontrolować przepływ elementów tablicy, co pozwala uniknąć problemów związanych z przekazywaniem dużych tablic jako parametrów metody.  
  
 Użyj [ICorProfilerInfo2:: EnumModuleFrozenObjects —](icorprofilerinfo2-enummodulefrozenobjects-method.md) , aby uzyskać wskaźnik do `ICorProfilerObjectEnum` interfejsu.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy profilowania](profiling-interfaces.md)
- [EnumModuleFrozenObjects, metoda](icorprofilerinfo2-enummodulefrozenobjects-method.md)
