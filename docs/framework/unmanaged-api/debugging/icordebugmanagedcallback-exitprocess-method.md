---
title: ICorDebugManagedCallback::ExitProcess — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
ms.openlocfilehash: 67f3e63b58e08a4b9ccfbd555e6edcdef0d00d90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688977"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a>ICorDebugManagedCallback::ExitProcess — Metoda

Powiadamia debugera o zakończeniu procesu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pProcess`  
 podczas Wskaźnik do obiektu ICorDebugProcess, który reprezentuje proces.  
  
## <a name="remarks"></a>Uwagi  

 Nie można kontynuować ze `ExitProcess` zdarzenia. To zdarzenie może być wyzwalane asynchronicznie do innych zdarzeń, gdy proces zostanie zatrzymany. Taka sytuacja może wystąpić, jeśli proces kończy się niepomyślnie, zazwyczaj z powodu pewnej siły zewnętrznej.  
  
 Jeśli środowisko uruchomieniowe języka wspólnego (CLR) już wysłało zarządzane wywołanie zwrotne, to zdarzenie zostanie opóźnione do momentu zwrócenia tego wywołania zwrotnego.  
  
 `ExitProcess`Zdarzenie jest jedynym zdarzeniem wyjścia/zwalniania, które ma zostać wywołane podczas zamykania.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug. idl, CorDebug. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorDebugManagedCallback — Interfejs](icordebugmanagedcallback-interface.md)
