---
title: ICorProfilerInfo2::GetStringLayout — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
ms.openlocfilehash: d141a78a953d4e0ab922535ad2363c79f2e18ecd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727045"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>ICorProfilerInfo2::GetStringLayout — Metoda

Pobiera informacje o układzie obiektu ciągu. Ta metoda jest przestarzała w .NET Framework 4 i jest zastępowana przez metodę [ICorProfilerInfo3:: GetStringLayout2 —](icorprofilerinfo3-getstringlayout2-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>Parametry  

 `pBufferLengthOffset`  
 określoną Wskaźnik do przesunięcia lokalizacji względem `ObjectID` wskaźnika, który przechowuje długość ciągu. Długość jest przechowywana jako `DWORD` .  
  
> [!NOTE]
> Ten parametr zwraca długość samego ciągu, a nie długość buforu. Długość buforu nie jest już dostępna.  
  
 `PStringLengthOffset`  
 określoną Wskaźnik do przesunięcia lokalizacji względem `ObjectID` wskaźnika, w którym jest przechowywana długość ciągu. Długość jest przechowywana jako `DWORD` .  
  
 `pBufferOffset`  
 określoną Wskaźnik do przesunięcia buforu względem `ObjectID` wskaźnika, który przechowuje ciąg znaków dwubajtowych.  
  
## <a name="remarks"></a>Uwagi  

 `GetStringLayout`Metoda pobiera przesunięcia, względem `ObjectID` wskaźnika, lokalizacji, w których są przechowywane następujące elementy:  
  
- Długość buforu ciągu.  
  
- Długość samego ciągu.  
  
- Bufor, który zawiera rzeczywisty ciąg znaków dwubajtowych.  
  
 Ciągi mogą być zakończone wartością null.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo — Interfejs](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 — Interfejs](icorprofilerinfo2-interface.md)
