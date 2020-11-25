---
title: ICorDebugMDA::GetOSThreadId — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
ms.openlocfilehash: 80248bba6d11b8af07aa0517cb41c8a4f783b5e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710899"
---
# <a name="icordebugmdagetosthreadid-method"></a>ICorDebugMDA::GetOSThreadId — Metoda

Pobiera identyfikator wątku systemu operacyjnego, na którym jest wykonywany Asystent debugowania zarządzanego (MDA) reprezentowany przez [ICorDebugMDA](icordebugmda-interface.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pOsTid`  
 określoną Wskaźnik do identyfikatora wątku systemu operacyjnego.  
  
## <a name="remarks"></a>Uwagi  

 Wątek systemu operacyjnego jest używany zamiast ICorDebugThread, aby umożliwić sytuacje, w których zdarzenie MDA jest wywoływane w wątku macierzystym lub w zarządzanym wątku, które nie podano jeszcze kodu zarządzanego.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugMDA — Interfejs](icordebugmda-interface.md)
- [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
