---
title: ICorDebugThread2::GetTaskID — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetTaskID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetTaskID
helpviewer_keywords:
- ICorDebugThread2::GetTaskID method [.NET Framework debugging]
- GetTaskID method [.NET Framework debugging]
ms.assetid: 6ba3c6ee-4ba1-4c98-bf1e-8531acd3da09
topic_type:
- apiref
ms.openlocfilehash: 9b17a179745af65bde05527bd0157f3ce06c12c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678678"
---
# <a name="icordebugthread2gettaskid-method"></a>ICorDebugThread2::GetTaskID — Metoda

Pobiera identyfikator zadania uruchomionego w tym wątku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetTaskID (  
    [out] TASKID  *pTaskId  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pTaskId`  
 określoną Wskaźnik do identyfikatora zadania uruchomionego w wątku reprezentowanego przez ten obiekt ICorDebugThread2.  
  
## <a name="remarks"></a>Uwagi  

 Zadanie może być uruchomione tylko w wątku, jeśli wątek jest skojarzony z połączeniem. `GetTaskID` zwraca zero w `pTaskId` przypadku, gdy wątek nie jest skojarzony z połączeniem.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
