---
title: ICorProfilerCallback::AppDomainCreationStarted — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationStarted
helpviewer_keywords:
- AppDomainCreationStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationStarted method [.NET Framework profiling]
ms.assetid: b2a8240b-07fe-4859-bb2b-7d3adbfa0a9f
topic_type:
- apiref
ms.openlocfilehash: 901546c80c3bee32afddfa8e8cffbd2b679bc43b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685399"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a>ICorProfilerCallback::AppDomainCreationStarted — Metoda

Powiadamia profiler o tworzeniu domeny aplikacji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a>Parametry

- `appDomainId`

  \[w programie] identyfikuje domenę, która jest tworzona.
  
## <a name="remarks"></a>Uwagi  

 Identyfikator nie jest prawidłowy dla żadnego żądania informacji, dopóki nie zostanie wywołana metoda [ICorProfilerCallback:: AppDomainCreationFinished —](icorprofilercallback-appdomaincreationfinished-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerCallback — Interfejs](icorprofilercallback-interface.md)
