---
title: ICorProfilerCallback3::InitializeForAttach — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.InitializeForAttach Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type:
- apiref
ms.openlocfilehash: c85bba9a5d913820b69cbc214275b733a53197ee
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729450"
---
# <a name="icorprofilercallback3initializeforattach-method"></a>ICorProfilerCallback3::InitializeForAttach — Metoda

Wywoływane przez środowisko uruchomieniowe języka wspólnego (CLR), aby Profiler mógł zainicjować swój stan po operacji dołączania.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a>Parametry  

 `pCorProfilerInfoUnk`  
 podczas Wskaźnik interfejsu dla `ICorProfilerInfo*` interfejsu.  
  
 `pvClientData`  
 podczas Wskaźnik do danych przesłany do metody [IClrProfiling:: AttachProfiler —](iclrprofiling-attachprofiler-method.md) w jej `pvClientData` parametrze. Jeśli ten parametr ma wartość null, `cbClientData` będzie miał wartość 0 (zero). Środowisko CLR zwalnia tę pamięć po powrocie z programu `InitializeForAttach` .  
  
 `cbClientData`  
 podczas Rozmiar, w bajtach, danych, które `pvClientData` wskazują.  
  
## <a name="remarks"></a>Uwagi  

 Środowisko CLR wywołuje, `InitializeForAttach` aby dać profilerowi możliwość żądania wywołania zwrotnego.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerCallback — Interfejs](icorprofilercallback-interface.md)
- [ICorProfilerInfo3 — Interfejs](icorprofilerinfo3-interface.md)
- [Interfejsy profilowania](profiling-interfaces.md)
- [Profilowanie](index.md)
