---
title: ICorProfilerInfo::GetModuleMetaData — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
ms.openlocfilehash: 74df0fb412e7fb3d9f779391ec84f07a0379a2cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724120"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>ICorProfilerInfo::GetModuleMetaData — Metoda

Pobiera wystąpienie interfejsu metadanych, które mapuje do określonego modułu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a>Parametry  

 `moduleId`  
 podczas Identyfikator modułu, do którego zostanie zamapowana wystąpienie interfejsu.  
  
 `dwOpenFlags`  
 podczas Wartość wyliczenia [CorOpenFlags —](../metadata/coropenflags-enumeration.md) , która określa tryb otwierania plików manifestu. Tylko `ofRead` `ofWrite` `ofNoTransform` bity i są prawidłowe.  
  
 `riid`  
 podczas Identyfikator odwołania (GUID) interfejsu metadanych, którego wystąpienie zostanie pobrane. Zobacz [interfejsy metadanych](../metadata/metadata-interfaces.md) , aby uzyskać listę interfejsów.  
  
 `ppOut`  
 określoną Wskaźnik do adresu wystąpienia interfejsu metadanych.  
  
## <a name="remarks"></a>Uwagi  

 Możesz poproszenie o otwarcie metadanych w trybie odczytu/zapisu, ale spowoduje to wolniejsze wykonanie tego programu, ponieważ nie można zoptymalizować zmian wprowadzonych w metadanych, ponieważ znajdowały się one w kompilatorze.  
  
 Niektóre moduły (takie jak moduły zasobów) nie mają metadanych. W takich przypadkach zwróci `GetModuleMetaData` wartość HRESULT o wartości S_FALSE i wartość null w * `ppOut` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo — Interfejs](icorprofilerinfo-interface.md)
