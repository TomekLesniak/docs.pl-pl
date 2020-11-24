---
title: ICorProfilerInfo::GetILFunctionBody — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
ms.openlocfilehash: 337c4fd091ebf7c39f7eee2358ca4f4df239cce3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687531"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>ICorProfilerInfo::GetILFunctionBody — Metoda

Pobiera wskaźnik do treści metody w kodzie języka pośredniego firmy Microsoft (MSIL), rozpoczynając od jego nagłówka.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a>Parametry  

 `moduleId`  
 podczas Identyfikator modułu, w którym znajduje się funkcja.  
  
 `methodId`  
 podczas Token metadanych dla metody.  
  
 `ppMethodHeader`  
 określoną Wskaźnik do nagłówka metody.  
  
 `pcbMethodSize`  
 określoną Liczba całkowita określająca rozmiar metody.  
  
## <a name="remarks"></a>Uwagi  

 Metoda jest objęta zakresem przez moduł, w którym przebywa. Ponieważ `GetILFunctionBody` Metoda została zaprojektowana w celu zapewnienia narzędziu dostępu do kodu MSIL przed jego załadowaniem przez środowisko uruchomieniowe języka wspólnego (CLR), używa tokenu metadanych metody w celu znalezienia żądanego wystąpienia.  
  
 `GetILFunctionBody` może zwrócić CORPROF_E_FUNCTION_NOT_IL HRESULT, jeśli `methodId` wskazuje na metodę bez żadnego kodu MSIL (takie jak metoda abstrakcyjna lub metoda wywołania platformy (PInvoke).  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo — Interfejs](icorprofilerinfo-interface.md)
