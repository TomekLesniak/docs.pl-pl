---
title: ICorProfilerInfo2::EnumModuleFrozenObjects — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
ms.openlocfilehash: fe4f3a7355339c9b5adbe5de062f0a5688d81c23
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727188"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a>ICorProfilerInfo2::EnumModuleFrozenObjects — Metoda

Pobiera moduł wyliczający, który umożliwia iterację w odniesieniu do zablokowanych obiektów w określonym module. Ta metoda jest przestarzała.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Parametry  

 `moduleID`  
 podczas Identyfikator modułu zawierającego zamrożone obiekty, które mają zostać wyliczone.  
  
 `ppEnum`  
 określoną Wskaźnik do adresu interfejsu [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) , który wylicza zamrożone obiekty.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:** 3,5, 3,0 sp1, 3,0, 2,0 SP1, 2,0  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo — Interfejs](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 — Interfejs](icorprofilerinfo2-interface.md)
