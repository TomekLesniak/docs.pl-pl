---
title: ICorDebugProcess5::GetTypeLayout — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: 32277e8adcd4bb08c8d0480eb3b4e7e4b5949479
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723132"
---
# <a name="icordebugprocess5gettypelayout-method"></a>ICorDebugProcess5::GetTypeLayout — Metoda

Pobiera informacje o układzie obiektu w pamięci na podstawie jego identyfikatora typu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a>Parametry  

 `id`  
 podczas Token [COR_TYPEID](cor-typeid-structure.md) , który określa typ, którego układ jest żądany.  
  
 `pLayout`  
 określoną Wskaźnik do struktury [COR_TYPE_LAYOUT](cor-type-layout-structure.md) , która zawiera informacje o układzie obiektu w pamięci.  
  
## <a name="remarks"></a>Uwagi  

 `ICorDebugProcess5::GetTypeLayout`Metoda zawiera informacje o obiekcie w oparciu o [COR_TYPEID](cor-typeid-structure.md), który jest zwracany przez wiele innych metod [ICorDebugProcess5](icordebugprocess5-interface.md) . Informacje są dostarczane przez strukturę [COR_TYPE_LAYOUT](cor-type-layout-structure.md) , która jest wypełniana przez metodę.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [COR_TYPE_LAYOUT — Struktura](cor-type-layout-structure.md)
- [ICorDebugProcess5 — Interfejs](icordebugprocess5-interface.md)
- [Debugowanie — Interfejsy](debugging-interfaces.md)
