---
title: ICorDebugProcess2::GetThreadForTaskID — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetThreadForTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetThreadForTaskID
helpviewer_keywords:
- ICorDebugProcess2::GetThreadForTaskId method [.NET Framework debugging]
- GetThreadForTaskID method [.NET Framework debugging]
ms.assetid: 32d54a5b-8ad3-405b-a1b9-0936a3b49d1e
topic_type:
- apiref
ms.openlocfilehash: 2b18289af460f64085fedd7b32387ebcb8c51715
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713551"
---
# <a name="icordebugprocess2getthreadfortaskid-method"></a>ICorDebugProcess2::GetThreadForTaskID — Metoda

Pobiera wątek, w którym wykonywane jest zadanie o określonym identyfikatorze.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetThreadForTaskID (  
    [in]  TASKID            taskid,  
    [out] ICorDebugThread2  **ppThread  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `taskid`  
 podczas Identyfikator zadania.  
  
 `ppThread`  
 określoną Wskaźnik do adresu obiektu ICorDebugThread2, który reprezentuje wątek do pobrania.  
  
## <a name="remarks"></a>Uwagi  

 Na hoście można ustawić identyfikator zadania za pomocą metody [ICLRTask:: SetTaskIdentifier —](../hosting/iclrtask-settaskidentifier-method.md) .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
