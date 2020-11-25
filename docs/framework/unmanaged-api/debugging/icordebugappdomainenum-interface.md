---
title: ICorDebugAppDomainEnum, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
ms.openlocfilehash: 37b6bcb48681704e3db47f81a51a9d21f00dfb37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723197"
---
# <a name="icordebugappdomainenum-interface"></a>ICorDebugAppDomainEnum, interfejs

Dostarcza `Next` metodę, która zwraca określoną liczbę `ICorDebugAppDomainEnum` wartości, zaczynając od następnej lokalizacji w wyliczeniu. Ten interfejs jest podklasą elementu "ICorDebugEnum".  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Next, metoda](icordebugappdomainenum-next-method.md)|Pobiera określoną liczbę domen aplikacji z kolekcji, rozpoczynając od bieżącego położenia kursora.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebug — Interfejs](icordebug-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
