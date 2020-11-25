---
title: ICorProfilerObjectEnum::Clone — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
ms.openlocfilehash: df1d5881bccdb357b16c7f02cd090388e0f66273
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722807"
---
# <a name="icorprofilerobjectenumclone-method"></a>ICorProfilerObjectEnum::Clone — Metoda

Pobiera wskaźnik interfejsu do kopii tego interfejsu [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppEnum`  
 określoną Wskaźnik do wskaźnika interfejsu, który z kolei wskazuje na kopię tego `ICorProfilerObjectEnum` interfejsu. Kopia zachowuje swój własny stan wyliczenia niezależnie od tego. Jednak początkowa pozycja kursora kopii będzie taka sama jak pozycja bieżącego kursora tego modułu wyliczającego.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerObjectEnum — Interfejs](icorprofilerobjectenum-interface.md)
