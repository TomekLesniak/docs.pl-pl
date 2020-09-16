---
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: a276ecfe65ed9752f39ed68a36e8e17a24255508
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558319"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a>ICorProfilerInfo10:: EnumerateObjectReferences, Metoda

Podanym identyfikatorem ObjectID, wywołaniem zwrotnym i clientData, wylicza każde odwołanie do obiektu (jeśli istnieje).

## <a name="syntax"></a>Składnia

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a>Parametry

- `objectId`

  \[in] obiekt, na którym mają zostać wyliczone odwołania.

- `callback`

  \[w] funkcja, która zostanie wywołana z odwołaniami dla obiektu.

- `clientData`

  \[in] dane dostarczone przez profiler do przekazania do `callback` funkcji.

## <a name="remarks"></a>Uwagi

`EnumerateObjectReferences`Metoda jest podobna do [ObjectReferences —](icorprofilercallback-objectreferences-method.md), z tą różnicą, że przeprowadza odwołania na żądanie dla profilera zamiast wstępnie przydzielić tablicę do przechowywania odwołań.

## <a name="requirements"></a>Wymagania

**Platformy:** Zobacz [obsługiwane systemy operacyjne .NET Core](../../../core/install/windows.md?pivots=os-windows).

**Nagłówek:** CorProf. idl, CorProf. h

**Biblioteka:** CorGuids. lib

**Wersje .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo10, interfejs](icorprofilerinfo10-interface.md)
