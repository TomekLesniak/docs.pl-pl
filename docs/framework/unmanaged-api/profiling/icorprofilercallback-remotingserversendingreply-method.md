---
title: ICorProfilerCallback::RemotingServerSendingReply — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerSendingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type:
- apiref
ms.openlocfilehash: 1d876644ae35d13a481b01d9e0e5ff0d0764ca18
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713954"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a>ICorProfilerCallback::RemotingServerSendingReply — Metoda

Powiadamia program profilujący, że proces zakończył przetwarzanie żądania wywołania metody zdalnej i ma na celu przesłanie odpowiedzi za pośrednictwem kanału.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>Parametry  

 `pCookie`  
 podczas Wskaźnik do identyfikatora GUID, który będzie odpowiadał wartości podanej w [ICorProfilerCallback:: RemotingClientReceivingReply —](icorprofilercallback-remotingclientreceivingreply-method.md) w następujących warunkach:  
  
- Pliki cookie identyfikatorów GUID usług zdalnych są aktywne.  
  
- Kanał pomyślnie przesyła komunikat.  
  
- Pliki cookie identyfikatorów GUID są aktywne w procesie po stronie klienta.  
  
 Pozwala to na łatwe parowanie wywołań zdalnych i Tworzenie stosu wywołań logicznych.  
  
 `fIsAsync`  
 podczas Wartość, która jest, `true` Jeśli wywołanie jest asynchroniczne; w przeciwnym razie `false` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICorProfilerCallback — Interfejs](icorprofilercallback-interface.md)
