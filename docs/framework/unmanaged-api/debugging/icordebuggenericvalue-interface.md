---
title: ICorDebugGenericValue, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
ms.openlocfilehash: cfa0950ca2ef4e969258c147b762fa95e52a82e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705823"
---
# <a name="icordebuggenericvalue-interface"></a>ICorDebugGenericValue, interfejs

Podklasa elementu "ICorDebugValue", która odnosi się do wszystkich wartości. Ten interfejs zapewnia metody Get i Set dla wartości.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetValue — Metoda](icordebuggenericvalue-getvalue-method.md)|Kopiuje wartość do określonego buforu.|  
|[SetValue — Metoda](icordebuggenericvalue-setvalue-method.md)|Kopiuje nową wartość z określonego buforu.|  
  
## <a name="remarks"></a>Uwagi  

 `ICorDebugGenericValue` jest interfejsem podrzędnym, ponieważ nie jest zdalnie.  
  
 W przypadku typów referencyjnych wartością jest odwołanie, a nie zawartość odwołania.  
  
 Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
