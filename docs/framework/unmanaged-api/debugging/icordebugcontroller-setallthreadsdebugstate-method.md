---
title: ICorDebugController::SetAllThreadsDebugState — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
ms.openlocfilehash: d8375948be5820aaf6e879b82bcfde6471cccf3f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679900"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a>ICorDebugController::SetAllThreadsDebugState — Metoda

Ustawia stan debugowania wszystkich zarządzanych wątków w procesie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `state`  
 podczas Wartość wyliczenia "CorDebugThreadState —", która określa stan wątku na potrzeby debugowania.  
  
 `pExceptThisThread`  
 podczas Wskaźnik do obiektu "ICorDebugThread", który reprezentuje wątek, który ma zostać wykluczony z ustawienia stanu debugowania. Jeśli ta wartość jest równa null, żaden wątek nie jest wykluczony.  
  
## <a name="remarks"></a>Uwagi  

 `SetAllThreadsDebugState`Metoda może mieć wpływ na wątki, które nie są widoczne za pośrednictwem [metody EnumerateThreads —](icordebugcontroller-enumeratethreads-method.md), więc wątki, które zostały zawieszone przy użyciu `SetAllThreadsDebugState` metody, muszą zostać wznowione przy użyciu `SetAllThreadsDebugState` metody.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
