---
title: ICorProfilerCallback::Initialize — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
ms.openlocfilehash: 26df1599af247bd08d3702d4ef3c5aa2f648620c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720376"
---
# <a name="icorprofilercallbackinitialize-method"></a>ICorProfilerCallback::Initialize — Metoda

Wywołuje się, by zainicjować profiler kodu za każdym razem, gdy jest uruchomiona nowa aplikacja środowiska uruchomieniowego języka wspólnego (CLR).  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a>Parametry

- `pICorProfilerInfoUnk`

  \[in) wskaźnik do interfejsu [IUnknown](/cpp/atl/iunknown) , który profiler musi wykonać zapytanie o wskaźnik interfejsu [ICorProfilerInfo](icorprofilerinfo-interface.md) .  

## <a name="remarks"></a>Uwagi  

 `Initialize`Wywołanie jest jedyną możliwością, aby włączyć (lub wyłączyć) wywołania zwrotne, które są niezmienne. Po włączeniu wywołania zwrotnego przez `Initialize` wywołanie nie można go wyłączyć później za pomocą [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md). COR_PRF_MONITOR_IMMUTABLE wartość wyliczenia [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) wskazuje, które zdarzenia są niezmienne.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerCallback — Interfejs](icorprofilercallback-interface.md)
- [Shutdown, metoda](icorprofilercallback-shutdown-method.md)
