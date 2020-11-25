---
title: ICorProfilerInfo2::GetAppDomainStaticAddress — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
ms.openlocfilehash: 271f9f4fd0d85407aedf088ffb524fa6e0398e37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727214"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a>ICorProfilerInfo2::GetAppDomainStaticAddress — Metoda

Pobiera adres wskazanej domeny aplikacji — pole statyczne należące do zakresu określonej domeny aplikacji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parametry  

 `classId`  
 podczas Identyfikator klasy klasy, która zawiera wymagane pole domeny aplikacji.  
  
 `fieldToken`  
 podczas Token metadanych dla żądanego pola domeny aplikacji — statycznej.  
  
 `appDomainId`  
 podczas Identyfikator domeny aplikacji, która jest zakresem żądanego pola statycznego.  
  
 `ppAddress`  
 określoną Wskaźnik do adresu pola statycznego znajdującego się w określonej domenie aplikacji.  
  
## <a name="remarks"></a>Uwagi  

 `GetAppDomainStaticAddress`Metoda może zwracać jedną z następujących wartości:  
  
- CORPROF_E_DATAINCOMPLETE HRESULT, jeśli podane pole statyczne nie ma przypisanego adresu w określonym kontekście.  
  
- Adresy obiektów, które mogą znajdować się w stercie wyrzucania elementów bezużytecznych. Te adresy mogą stać się nieprawidłowe po wyrzucaniu elementów bezużytecznych, więc po wybraniu elementów bezużytecznych nie należy zakładać, że są one poprawne.  
  
 Przed ukończeniem konstruktora klasy klasy `GetAppDomainStaticAddress` zwraca CORPROF_E_DATAINCOMPLETE dla wszystkich pól statycznych, chociaż niektóre pola statyczne mogą już być zainicjowane i główne obiekty wyrzucania elementów bezużytecznych.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerInfo — Interfejs](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 — Interfejs](icorprofilerinfo2-interface.md)
