---
title: ICorDebugAppDomain::GetName — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
ms.openlocfilehash: 501a4543940437bfe2a6cb0952aed8184107150c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672165"
---
# <a name="icordebugappdomaingetname-method"></a>ICorDebugAppDomain::GetName — Metoda

Pobiera nazwę domeny aplikacji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `cchName`  
 podczas Rozmiar `szName` tablicy. Ustaw tę wartość na zero, aby ustawić tę metodę w trybie zapytania.  
  
 `pcchName`  
 określoną Wskaźnik do rozmiaru nazwy lub liczby znaków faktycznie zwracanych przez `szName` . W trybie zapytania ta wartość umożliwia obiektowi wywołującemu określenie, jak duży bufor ma zostać przydzielony do nazwy.  
  
 `szName`  
 określoną Tablica, w której jest przechowywana nazwa domeny aplikacji.  
  
## <a name="remarks"></a>Uwagi  

 Debuger wywołuje `GetName` metodę raz, aby uzyskać rozmiar buforu wymaganego dla nazwy. Debuger przydziela bufor, a następnie wywołuje metodę przy drugim czasie, aby wypełnić bufor. Pierwsze wywołanie, aby uzyskać rozmiar nazwy, jest określany jako *tryb zapytania*.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
