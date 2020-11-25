---
title: ICorDebugFunction2::GetJMCStatus — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 747f165a98dfd1264ea58d61aaa1615c6d71e073
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726299"
---
# <a name="icordebugfunction2getjmcstatus-method"></a>ICorDebugFunction2::GetJMCStatus — Metoda

Pobiera wartość wskazującą, czy funkcja reprezentowana przez ten obiekt ICorDebugFunction2 jest oznaczona jako kod użytkownika.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pbIsJustMyCode`  
 określoną Wskaźnik do wartości logicznej, która jest `true` oznaczona jako kod użytkownika; w przeciwnym razie wartość to `false` .  
  
## <a name="remarks"></a>Uwagi  

 Jeśli funkcja reprezentowana przez to `ICorDebugFunction2` nie może być debugowana, `pbIsJustMyCode` będzie zawsze `false` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
