---
title: ICorProfilerModuleEnum::Clone — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type:
- apiref
ms.openlocfilehash: ae9f6b7865a80e3edc4cae8fd1298e5eed864377
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722833"
---
# <a name="icorprofilermoduleenumclone-method"></a>ICorProfilerModuleEnum::Clone — Metoda

Pobiera wskaźnik interfejsu do kopii tego interfejsu [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppEnum`  
 określoną Wskaźnik do wskaźnika interfejsu, który z kolei wskazuje na kopię tego interfejsu [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) . Kopia modułu wyliczającego utrzymuje swój własny stan wyliczenia niezależnie od tego modułu wyliczającego. Jednak początkowa pozycja kursora kopii jest taka sama jak pozycja bieżącego kursora tego modułu wyliczającego.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerModuleEnum — Interfejs](icorprofilermoduleenum-interface.md)
- [Interfejsy profilowania](profiling-interfaces.md)
