---
title: ICorDebugThread::GetHandle — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
ms.openlocfilehash: 5debd09f3ca0b4562f62913f9530cc4fa6f9110b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728033"
---
# <a name="icordebugthreadgethandle-method"></a>ICorDebugThread::GetHandle — Metoda

Pobiera bieżące dojście dla aktywnej części tego ICorDebugThread.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `phThreadHandle`  
 określoną Wskaźnik do elementu HTHREAD, który jest uchwytem aktywnej części tego wątku.  
  
## <a name="remarks"></a>Uwagi  

 Dojście może ulec zmianie, gdy proces jest wykonywany i może się różnić w różnych częściach wątku.  
  
 To dojście jest własnością interfejsu API debugowania. Debuger powinien go zduplikować przed użyciem.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
