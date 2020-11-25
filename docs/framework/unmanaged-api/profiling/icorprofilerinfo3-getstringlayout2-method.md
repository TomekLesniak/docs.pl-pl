---
title: ICorProfilerInfo3::GetStringLayout2 — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetStringLayout2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type:
- apiref
ms.openlocfilehash: dc4df7e7cb93f137013d0a0e4d805c7563d4fe1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697899"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a>ICorProfilerInfo3::GetStringLayout2 — Metoda

Pobiera informacje o układzie obiektu ciągu. Ta metoda zastępuje metodę [ICorProfilerInfo2:: GetStringLayout —](icorprofilerinfo2-getstringlayout-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>Parametry  

 `pStringLengthOffset`  
 określoną Wskaźnik do przesunięcia lokalizacji względem `ObjectID` wskaźnika, w którym jest przechowywana długość ciągu. Długość jest przechowywana jako `DWORD` .  
  
 `pBufferOffset`  
 określoną Wskaźnik do przesunięcia buforu, względem `ObjectID` wskaźnika, który przechowuje ciąg znaków dwubajtowych.  
  
## <a name="remarks"></a>Uwagi  

 Ciągi mogą lub nie mogą być zakończone znakiem null.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo3 — Interfejs](icorprofilerinfo3-interface.md)
- [Interfejsy profilowania](profiling-interfaces.md)
