---
title: ICorProfilerFunctionControl — Interfejs
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
ms.openlocfilehash: 733a8f0bc7e8c19823827297a50f9c6906614ca7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698393"
---
# <a name="icorprofilerfunctioncontrol-interface"></a>ICorProfilerFunctionControl — Interfejs

Dostarcza metody, które umożliwiają profilerowi kodu komunikowanie się ze środowiskiem uruchomieniowym języka wspólnego (CLR) w celu kontrolowania, jak kompilator JIT powinien generować kod podczas ponownego kompilowania określonej metody.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[SetCodegenFlags, metoda](icorprofilerfunctioncontrol-setcodegenflags-method.md)|Ustawia co najmniej jedną flagę z wyliczenia [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) , aby kontrolować generowanie kodu dla funkcji rekompilowanej just-in-Time (JIT).|  
|[SetILFunctionBody — Metoda](icorprofilerfunctioncontrol-setilfunctionbody-method.md)|Zastępuje treść wspólnego języka pośredniego (CIL) metody.|  
|[SetILInstrumentedCodeMap — Metoda](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|Ustawia mapę kodu dla określonej funkcji przy użyciu określonych wpisów mapy typowego języka pośredniego (CIL).|  
  
## <a name="remarks"></a>Uwagi  

 `ICorProfilerFunctionControl`Interfejs zapewnia metody kontrolujące generowanie kodu dla pojedynczej ponownie skompilowanej funkcji. Profiler uzyskuje wystąpienie tego interfejsu za pomocą wywołania zwrotnego [ICorProfilerCallback4:: GetReJITParameters —](icorprofilercallback4-getrejitparameters-method.md) . Każde wystąpienie `ICorProfilerFunctionControl` formantów kontroluje wszystkie wystąpienia jednej funkcji.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo4 — Interfejs](icorprofilerinfo4-interface.md)
- [Interfejsy profilowania](profiling-interfaces.md)
- [EnumJITedFunctions2, metoda](icorprofilerinfo4-enumjitedfunctions2-method.md)
