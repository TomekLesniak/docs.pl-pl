---
title: ICorProfilerInfo::GetTokenAndMetadataFromFunction — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type:
- apiref
ms.openlocfilehash: 8e03eefc3758347389be4af6d53921480ee40263
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724081"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a>ICorProfilerInfo::GetTokenAndMetadataFromFunction — Metoda

Pobiera token metadanych i wystąpienie interfejsu metadanych, których można użyć względem tokenu dla określonej funkcji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a>Parametry  

 `functionId`  
 podczas Identyfikator funkcji, dla której ma zostać pobrany token metadanych i interfejs metadanych.  
  
 `riid`  
 podczas Identyfikator odwołania interfejsu metadanych, dla którego ma zostać pobrane wystąpienie.  
  
 `ppImport`  
 określoną Wskaźnik do adresu wystąpienia interfejsu metadanych, który może być używany w odniesieniu do tokenu dla określonej funkcji.  
  
 `pToken`  
 określoną Wskaźnik do tokenu metadanych dla określonej funkcji.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo — Interfejs](icorprofilerinfo-interface.md)
