---
title: 'ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated, Metoda'
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: 248d2f749ddcbd772313558af2b2721f4d1c0f58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723093"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a>ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated, Metoda

[Obsługiwane w .NET Framework 4.6.1 i nowszych wersjach]  
  
 Powiadamia profiler za każdym razem, gdy zostanie zaktualizowany strumień symboli skojarzony z modułem w pamięci.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a>Parametry  

 podczas `moduleId`  
 Identyfikator modułu w pamięci, którego strumień symboli został zaktualizowany.  
  
## <a name="remarks"></a>Uwagi  

 To wywołanie zwrotne jest kontrolowane przez ustawienie flagi maski zdarzeń [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) podczas wywoływania metody [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .  
  
> [!NOTE]
> To zdarzenie nie jest obecnie wywoływane dla symboli niejawnie utworzonych lub zmodyfikowanych za pośrednictwem <xref:System.Reflection.Emit> interfejsów API.  
  
 Nawet jeśli symbole są dostarczane z góry w wywołaniu jednego z przeciążeń metod zarządzanych, <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> które zawierają `rawSymbolStore` argument, aby określić symbole dla zestawu, środowisko uruchomieniowe może nie skojarzyć danych symbolicznych z modułem do momentu wystąpienia wywołania zwrotnego [ModuleLoadFinished —](icorprofilercallback-moduleloadfinished-method.md) . To zdarzenie umożliwia późniejsze zbieranie symboli dla takich modułów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ModuleLoadFinished, metoda](icorprofilercallback-moduleloadfinished-method.md)
- [SetEventMask2, metoda](icorprofilerinfo5-seteventmask2-method.md)
- [ICorProfilerCallback7, interfejs](icorprofilercallback7-interface.md)
