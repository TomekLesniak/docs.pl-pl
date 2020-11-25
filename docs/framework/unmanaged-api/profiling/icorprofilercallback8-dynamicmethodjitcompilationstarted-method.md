---
title: ICorProfilerCallback8::D ynamicMethodJITCompilationStarted Metoda
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 46a25fc6e9119481f728275e0569429cc6c46dc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725433"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>ICorProfilerCallback8::D ynamicMethodJITCompilationStarted Metoda

[Obsługiwane w .NET Framework 4,7 i nowszych wersjach]  
  
Powiadamia profiler za każdym razem, gdy została rozpoczęta kompilacja JIT metody dynamicznej.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a>Parametry  

podczas `functionId`  
Identyfikator funkcji w pamięci, dla której uruchomiono kompilację JIT.

[w] `fIsSafeToBlock` 
 `true` Aby wskazać, że blokowanie może spowodować, że środowisko uruchomieniowe będzie oczekiwać na zwrócenie przez wątek wywołujący z tego wywołania zwrotnego; `false`, aby wskazać, że blokowanie nie wpłynie na działanie środowiska uruchomieniowego.  

[w] `pILHeader` Wskaźnik do pierwszego bajtu nagłówka IL metody.

[w] `cbILHeader` Liczba bajtów w nagłówku IL.

## <a name="remarks"></a>Uwagi  

To wywołanie zwrotne jest wyzwalane za każdym razem, gdy metoda dynamiczna jest skompilowana w trybie JIT. Obejmuje to różne metody pośredniczące IL i LCG. Celem jest zapewnienie autorom profilera wystarczającej ilości informacji do zidentyfikowania skompilowanej metody dla użytkowników.

> [!NOTE]
> `functionId` wartości nie można użyć do rozpoznania ich tokenów metadanych, ponieważ metody dynamiczne nie mają metadanych.

`pILHeader`Wskaźnik jest prawidłowy tylko podczas wywołania zwrotnego.

## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Zobacz także

- [DynamicMethodJITCompilationFinished, metoda](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [ICorProfilerCallback8, interfejs](icorprofilercallback8-interface.md)
