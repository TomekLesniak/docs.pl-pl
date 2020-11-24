---
title: ICorDebugStackWalk — Interfejs
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: b37a89c0a86df49c894dc43676f8feafb80f5c95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687518"
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk — Interfejs

Dostarcza metody pobierania zarządzanych metod, lub ramek, znajdujących się na stosie wątku.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetContext — Metoda](icordebugstackwalk-getcontext-method.md)|Zwraca kontekst dla bieżącej ramki w `ICorDebugStackWalk` obiekcie.|  
|[SetContext, metoda](icordebugstackwalk-setcontext-method.md)|Ustawia `ICorDebugStackWalk` bieżący kontekst obiektu na prawidłowy kontekst dla wątku.|  
|[Next, metoda](icordebugstackwalk-next-method.md)|Przenosi `ICorDebugStackWalk` obiekt do następnej ramki.|  
|[GetFrame, metoda](icordebugstackwalk-getframe-method.md)|Pobiera bieżącą ramkę w `ICorDebugStackWalk` obiekcie.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
> Ten interfejs nie obsługuje wywoływania zdalnego na wielu maszynach ani wielu procesów.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Debugowanie — Interfejsy](debugging-interfaces.md)
- [Debugowanie](index.md)
