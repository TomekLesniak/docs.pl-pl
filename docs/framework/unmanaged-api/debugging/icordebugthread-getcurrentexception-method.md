---
title: ICorDebugThread::GetCurrentException — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
ms.openlocfilehash: c21be7b062b7e2d4129bafabae004351442ab853
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728059"
---
# <a name="icordebugthreadgetcurrentexception-method"></a>ICorDebugThread::GetCurrentException — Metoda

Pobiera wskaźnik interfejsu do obiektu ICorDebugValue, który reprezentuje wyjątek, który jest aktualnie generowany przez kod zarządzany.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `ppExceptionObject`  
 określoną Wskaźnik do adresu `ICorDebugValue` obiektu, który reprezentuje wyjątek, który jest aktualnie generowany przez kod zarządzany.  
  
## <a name="remarks"></a>Uwagi  

 Obiekt wyjątku będzie istniał od momentu zgłoszenia wyjątku do końca `catch` bloku. Ocena funkcji, która jest wykonywana przez metody ICorDebugEval, spowoduje wyczyszczenie obiektu wyjątku podczas instalacji i przywrócenie go po zakończeniu.  
  
 Wyjątki mogą być zagnieżdżane (na przykład, jeśli wyjątek jest zgłaszany w filtr lub w ocenie funkcji), więc może istnieć wiele oczekujących wyjątków w pojedynczym wątku. `GetCurrentException` zwraca najnowszy wyjątek.  
  
 Obiekt i typ wyjątku mogą ulec zmianie w całym okresie istnienia wyjątku. Na przykład po wystąpieniu wyjątku typu x, środowisko uruchomieniowe języka wspólnego (CLR) może za mało pamięci i podnieść go do wyjątku braku pamięci.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
