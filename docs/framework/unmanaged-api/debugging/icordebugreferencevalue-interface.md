---
title: ICorDebugReferenceValue, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
ms.openlocfilehash: 343e504e086e740236d7b5977452cc0d789883fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728410"
---
# <a name="icordebugreferencevalue-interface"></a>ICorDebugReferenceValue, interfejs

Dostarcza metody, które zarządzają wartością, która jest odwołaniem do obiektu. (Oznacza to, że ten interfejs zapewnia metody, które zarządzają wskaźnikiem). Ten interfejs implementuje "ICorDebugValue".  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Dereference, metoda](icordebugreferencevalue-dereference-method.md)|Pobiera obiekt, do którego istnieje odwołanie.|  
|[DereferenceStrong, metoda](icordebugreferencevalue-dereferencestrong-method.md)|Nie zaimplementowano. Nie wywołuj tej metody.|  
|[GetValue — Metoda](icordebugreferencevalue-getvalue-method.md)|Pobiera bieżący adres pamięci obiektu, do którego istnieje odwołanie.|  
|[IsNull, metoda](icordebugreferencevalue-isnull-method.md)|Pobiera wartość wskazującą, czy jest to `ICorDebugReferenceValue` wartość null, w takim przypadku nie `ICorDebugReferenceValue` wskazuje na obiekt.|  
|[SetValue — Metoda](icordebugreferencevalue-setvalue-method.md)|Ustawia bieżący adres pamięci. Oznacza to, że ta metoda ustawia ten element tak, `ICorDebugReferenceValue` aby wskazywał obiekt.|  
  
## <a name="remarks"></a>Uwagi  

 Środowisko uruchomieniowe języka wspólnego (CLR) może wykonywać odzyskiwanie pamięci na obiektach, gdy debugowany proces jest kontynuowany. Wyrzucanie elementów bezużytecznych może przenosić obiekty w pamięci. `ICorDebugReferenceValue`Program będzie współpracować z wyrzucaniem elementów bezużytecznych, aby informacje były aktualizowane po wyrzucaniu elementów bezużytecznych lub zostaną unieważnione niejawnie przed wyrzucaniem elementów bezużytecznych.  
  
 `ICorDebugReferenceValue`Obiekt może być niejawnie unieważniony po dalszym debugowanym procesie. Pochodny element "ICorDebugHandleValue" nie jest unieważniony, dopóki nie zostanie jawnie wystawiony lub ujawniony.  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
