---
title: ICorProfilerInfo2::GetArrayObjectInfo — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetArrayObjectInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type:
- apiref
ms.openlocfilehash: a1e321e141059ccf1da7292d28e7099418a5134e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727201"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a>ICorProfilerInfo2::GetArrayObjectInfo — Metoda

Pobiera szczegółowe informacje o obiekcie array.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a>Parametry  

 `objectId`  
 podczas Identyfikator prawidłowego obiektu tablicy.  
  
 `cDimensions`  
 podczas Ranga (liczba wymiarów) tablicy.  
  
 `pDimensionSizes`  
 określoną Tablica zawierająca liczby całkowite, z których każdy reprezentuje rozmiar wymiaru tablicy.  
  
 `pDimensionLowerBounds`  
 określoną Tablica zawierająca liczby całkowite, z których każda reprezentuje dolną granicę wymiaru tablicy.  
  
 `ppData`  
 określoną Wskaźnik na adres nieprzetworzonego buforu dla tablicy, który jest ustalany zgodnie z Konwencją języka C++.  
  
## <a name="remarks"></a>Uwagi  

 `pDimensionSizes`I `pDimensionLowerBounds` są to tablice równoległe, dlatego elementy znajdujące się w tym samym indeksie w każdej tablicy są cechami tej samej jednostki.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo — Interfejs](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 — Interfejs](icorprofilerinfo2-interface.md)
