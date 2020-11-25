---
title: ICorDebugClass2, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
ms.openlocfilehash: ce3f289ae914817071fad5274c45d1e5fae71a06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717984"
---
# <a name="icordebugclass2-interface"></a>ICorDebugClass2, interfejs

Reprezentuje klasę generyczną lub klasę z parametrem metody typu <xref:System.Type> . Ten interfejs rozszerza [ICorDebugClass](icordebugclass-interface.md).  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetParameterizedType, metoda](icordebugclass2-getparameterizedtype-method.md)|Pobiera deklarację typu dla tej klasy.|  
|[SetJMCStatus — Metoda](icordebugclass2-setjmcstatus-method.md)|Dla każdej metody tej klasy ustawia wartość wskazującą, czy metoda jest kodem zdefiniowanym przez użytkownika.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugClass, interfejs](icordebugclass-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
