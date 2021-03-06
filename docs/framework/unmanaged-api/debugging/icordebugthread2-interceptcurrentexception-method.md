---
title: ICorDebugThread2::InterceptCurrentException — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.InterceptCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::InterceptCurrentException
helpviewer_keywords:
- InterceptCurrentException method [.NET Framework debugging]
- ICorDebugThread2::InterceptCurrentException method [.NET Framework debugging]
ms.assetid: 536d2357-1b97-49e0-a10c-c860aed74e6e
topic_type:
- apiref
ms.openlocfilehash: 96e3a90bcb7700915bfd3618d7bae40c0ff64a75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678600"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a>ICorDebugThread2::InterceptCurrentException — Metoda

Umożliwia debugerowi przechwycenie bieżącego wyjątku w tym wątku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pFrame`  
 podczas Wskaźnik do elementu ICorDebugFrame, który reprezentuje aktywną ramkę stosu.  
  
## <a name="remarks"></a>Uwagi  

 `InterceptCurrentException`Metodę można wywołać między wywołaniem zwrotnym wyjątku ([ICorDebugManagedCallback:: Exception](icordebugmanagedcallback-exception-method.md) lub [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md)) i skojarzonym wywołaniem do [ICorDebugController:: Continue](icordebugcontroller-continue-method.md).  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
