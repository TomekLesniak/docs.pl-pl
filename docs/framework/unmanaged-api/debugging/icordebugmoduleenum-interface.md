---
title: ICorDebugModuleEnum, interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
ms.openlocfilehash: 08d16393a04888cd3f1a03fa209a1fceac28520b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724757"
---
# <a name="icordebugmoduleenum-interface"></a>ICorDebugModuleEnum, interfejs

Implementuje metody ICorDebugEnum i wylicza tablice ICorDebugModule.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Next, metoda](icordebugmoduleenum-next-method.md)|Pobiera określoną liczbę `ICorDebugModule` wystąpień z wyliczenia, rozpoczynając od bieżącego położenia.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
