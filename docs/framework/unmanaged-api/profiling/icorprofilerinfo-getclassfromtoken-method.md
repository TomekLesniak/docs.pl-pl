---
title: ICorProfilerInfo::GetClassFromToken — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 7d9fe7d6d5c5af32be22ba19b52e7d40033a6eb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706752"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a>ICorProfilerInfo::GetClassFromToken — Metoda

Pobiera identyfikator klasy, z uwzględnieniem tokenu metadanych. Ta metoda jest przestarzała w .NET Framework w wersji 2,0. Zamiast tego użyj [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs —](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a>Parametry  

 `moduleID`  
 podczas Identyfikator modułu, który zawiera klasę.  
  
 `typeDef`  
 podczas `mdTypeDef` Token metadanych, który odwołuje się do klasy.  
  
 `cTypeArgs`  
 określoną Wskaźnik do identyfikatora klasy.  
  
## <a name="remarks"></a>Uwagi  

 Ta metoda jest przestarzała; Zamiast tego należy używać `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` dla wszystkich typów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:** 1,0, 1,1  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo — Interfejs](icorprofilerinfo-interface.md)
