---
title: ICorDebugController::IsRunning — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugController.IsRunning
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::IsRunning
helpviewer_keywords:
- IsRunning method [.NET Framework debugging]
- ICorDebugController::IsRunning method [.NET Framework debugging]
ms.assetid: b33ff059-40c4-4dfe-9cb2-21bfed2de0b0
topic_type:
- apiref
ms.openlocfilehash: 73ed86ee12b02d292dc6dfc1d652459a679f81ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679940"
---
# <a name="icordebugcontrollerisrunning-method"></a>ICorDebugController::IsRunning — Metoda

Pobiera wartość wskazującą, czy wątki w procesie są obecnie uruchomione swobodnie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pbRunning`  
 określoną Wskaźnik do wartości, która jest, `true` Jeśli wątki w procesie działają swobodnie; w przeciwnym razie `false` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
