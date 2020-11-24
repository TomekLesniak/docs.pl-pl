---
title: ICorDebugThread::CreateEval — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
ms.openlocfilehash: 1c0037530ae4f40be5bef4da8f398afe5f2bbb91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688292"
---
# <a name="icordebugthreadcreateeval-method"></a>ICorDebugThread::CreateEval — Metoda

Tworzy obiekt ICorDebugEval, który zbiera i udostępnia funkcje tego ICorDebugThread.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppEval`  
 określoną Wskaźnik do adresu `ICorDebugEval` obiektu, który zbiera i udostępnia funkcjonalność tego wątku.  
  
## <a name="remarks"></a>Uwagi  

 Obiekt oceny wypycha nowy łańcuch w wątku przed wykonaniem jego obliczenia. Spowoduje to przerwanie obliczeń aktualnie wykonywanych na wątku do momentu zakończenia szacowania.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
