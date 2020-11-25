---
title: ICorProfilerCallback::JITInlining — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
ms.openlocfilehash: cf68594620b24f2a5823aa423c5911f2d9d6b328
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725498"
---
# <a name="icorprofilercallbackjitinlining-method"></a>ICorProfilerCallback::JITInlining — Metoda

Powiadamia profiler, że kompilator just in Time (JIT) ma wstawić funkcję w wierszu z inną funkcją.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a>Parametry  

 `callerId`  
 podczas Identyfikator funkcji, do której `calleeId` zostanie wstawiona funkcja.  
  
 `calleeId`  
 podczas Identyfikator funkcji, która ma zostać wstawiona.  
  
 `pfShouldInline`  
 [out] `true` , aby zezwolić na wstawianie; w przeciwnym razie `false` .  
  
## <a name="remarks"></a>Uwagi  

 Profiler można ustawić tak, aby `pfShouldInline` `false` uniemożliwić `calleeId` Wstawianie funkcji do `callerId` funkcji. Dodatkowo profiler może globalnie wyłączyć wstawianie wbudowane przy użyciu wartości COR_PRF_DISABLE_INLINING [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) Enumeration.  
  
 Wbudowane funkcje nie zgłaszają zdarzeń do wprowadzenia lub opuszczenia. W związku z tym profiler musi mieć ustawioną wartość `pfShouldInline` `false` w celu wygenerowania dokładnej wykres wywołań. Ustawienie `pfShouldInline` ma `false` wpływ na wydajność, ponieważ Wstawianie wbudowane zwykle zwiększa szybkość i zmniejsza liczbę oddzielnych zdarzeń kompilacji JIT dla włożonej metody.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerCallback — Interfejs](icorprofilercallback-interface.md)
