---
title: ICorProfilerInfo10::SuspendRuntime
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.SuspendRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 121ed0401628193f6e2fe632a124c08aad7bd1b4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551442"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a>ICorProfilerInfo10:: SuspendRuntime, Metoda

Wstrzymuje środowisko uruchomieniowe bez wykonywania operacji GC.

## <a name="syntax"></a>Składnia

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a>Wymagania

**Platformy:** Zobacz [obsługiwane systemy operacyjne .NET Core](../../../core/install/windows.md?pivots=os-windows).

**Nagłówek:** CorProf. idl, CorProf. h

**Biblioteka:** CorGuids. lib

**Wersje .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo10, interfejs](icorprofilerinfo10-interface.md)
