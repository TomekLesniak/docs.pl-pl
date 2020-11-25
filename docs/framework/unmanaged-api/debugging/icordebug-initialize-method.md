---
title: ICorDebug::Initialize — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebug.Initialize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type:
- apiref
ms.openlocfilehash: 5cdd89ebdbb5abb9b001c1489a54bfb867808c5c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723431"
---
# <a name="icordebuginitialize-method"></a>ICorDebug::Initialize — Metoda

Inicjuje `ICorDebug` obiekt.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a>Uwagi  

 Debuger musi wywołać `Initialize` w czasie tworzenia, aby zainicjować usługi debugowania. Ta metoda musi być wywoływana przed wywołaniem jakiejkolwiek innej metody dla `ICorDebug` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebug — Interfejs](icordebug-interface.md)
