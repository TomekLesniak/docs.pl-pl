---
title: ICorDebugThread::GetDebugState — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
ms.openlocfilehash: 746fef3629e6573d7dfe47d5a3fcf9ee9a1d4250
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728046"
---
# <a name="icordebugthreadgetdebugstate-method"></a>ICorDebugThread::GetDebugState — Metoda

Pobiera bieżący stan debugowania tego obiektu ICorDebugThread.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pState`  
 określoną Wskaźnik do bitowej kombinacji wartości wyliczenia CorDebugThreadState —, który opisuje bieżący stan debugowania tego wątku.  
  
## <a name="remarks"></a>Uwagi  

 Jeśli proces jest aktualnie zatrzymany, `pState` reprezentuje stan debugowania dla tego wątku, jeśli proces ma być kontynuowany, a nie z rzeczywistym bieżącym stanem tego wątku.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
