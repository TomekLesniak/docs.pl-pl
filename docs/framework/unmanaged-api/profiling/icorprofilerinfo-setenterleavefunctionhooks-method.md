---
title: ICorProfilerInfo::SetEnterLeaveFunctionHooks — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
ms.openlocfilehash: 18aed5c5314fc1057767b599c538952a1d4d6b57
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722235"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a>ICorProfilerInfo::SetEnterLeaveFunctionHooks — Metoda

Określa funkcje zaimplementowane przez profiler, które mają być wywoływane w podpunktach "Enter", "urlop" i "tailcall" punktów zarządzanych funkcji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a>Parametry  

 `pFuncEnter`  
 podczas Wskaźnik do implementacji, który ma być używany jako wywołanie zwrotne [FunctionEnter —](functionenter-function.md) .  
  
 `pFuncLeave`  
 podczas Wskaźnik do implementacji, który ma być używany jako wywołanie zwrotne [FunctionLeave —](functionleave-function.md) .  
  
 `pFuncTailcall`  
 podczas Wskaźnik do implementacji, który ma być używany jako wywołanie zwrotne [FunctionTailcall —](functiontailcall-function.md) .  
  
## <a name="remarks"></a>Uwagi  

 W .NET Framework w wersji 1,0, każdy wskaźnik funkcji może mieć wartość null, aby wyłączyć odpowiednie wywołanie zwrotne.  
  
 Tylko jeden zestaw wywołań zwrotnych może być aktywny w danym momencie. W takim przypadku, jeśli Profiler wywołuje zarówno element `SetEnterLeaveFunctionHooks` , jak i [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2 —](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), `SetEnterLeaveFunctionHooks2` ma pierwszeństwo.  
  
 `SetEnterLeaveFunctionHooks`Metodę można wywołać tylko z [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) wywołania zwrotnego profilera.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo — Interfejs](icorprofilerinfo-interface.md)
