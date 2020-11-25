---
title: ICorDebugValue2::GetExactType — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: cb5bec66ab02de248109d8aaf444a93e67c2c6d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720363"
---
# <a name="icordebugvalue2getexacttype-method"></a>ICorDebugValue2::GetExactType — Metoda

Pobiera wskaźnik interfejsu do obiektu "ICorDebugType", który reprezentuje <xref:System.Type> tę wartość.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppType`  
 określoną Wskaźnik do adresu `ICorDebugType` obiektu, który reprezentuje <xref:System.Type> wartość reprezentowaną przez ten obiekt "ICorDebugValue2".  
  
## <a name="remarks"></a>Uwagi  

 Metoda oparta na typach ogólnych `GetExactType` zastępuje metody [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) i [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , z których każdy zwraca informacje o typie wartości.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
