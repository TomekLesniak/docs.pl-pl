---
title: ICorProfilerCallback::RemotingClientInvocationFinished — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
ms.openlocfilehash: d41ccd30707eba269bbac7231e06792363615544
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719323"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="550a5-102">ICorProfilerCallback::RemotingClientInvocationFinished — Metoda</span><span class="sxs-lookup"><span data-stu-id="550a5-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>

<span data-ttu-id="550a5-103">Powiadamia program profilujący, że wywołanie komunikacji zdalnej zostało uruchomione w celu ukończenia na kliencie.</span><span class="sxs-lookup"><span data-stu-id="550a5-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="550a5-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="550a5-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="550a5-105">Uwagi</span><span class="sxs-lookup"><span data-stu-id="550a5-105">Remarks</span></span>  

 <span data-ttu-id="550a5-106">Jeśli wywołanie komunikacji zdalnej było synchroniczne, zostało także uruchomione na serwerze.</span><span class="sxs-lookup"><span data-stu-id="550a5-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="550a5-107">Jeśli wywołanie komunikacji zdalnej było asynchroniczne, odpowiedź może być nadal oczekiwana, gdy wywołanie jest obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="550a5-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="550a5-108">Jeśli oczekiwana jest odpowiedź, nastąpi wywołanie metody [ICorProfilerCallback:: RemotingClientReceivingReply —](icorprofilercallback-remotingclientreceivingreply-method.md) i dodatkowego wywołania do `RemotingClientInvocationFinished` , aby wskazać wymagane pomocnicze przetwarzanie wywołania asynchronicznego.</span><span class="sxs-lookup"><span data-stu-id="550a5-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="550a5-109">Każda z następujących par wywołań zwrotnych nastąpi w tym samym wątku:</span><span class="sxs-lookup"><span data-stu-id="550a5-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="550a5-110">`RemotingClientInvocationStarted` i [ICorProfilerCallback:: RemotingClientSendingMessage —](icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="550a5-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="550a5-111">[ICorProfilerCallback:: RemotingClientReceivingReply —](icorprofilercallback-remotingclientreceivingreply-method.md) i [ICorProfilerCallback:: RemotingClientInvocationFinished —](icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="550a5-111">[ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="550a5-112">[ICorProfilerCallback:: RemotingServerInvocationReturned —](icorprofilercallback-remotingserverinvocationreturned-method.md) i [ICorProfilerCallback:: RemotingServerSendingReply —](icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="550a5-112">[ICorProfilerCallback::RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="550a5-113">Należy pamiętać o następujących problemach z wywołaniami zwrotnymi usług zdalnych:</span><span class="sxs-lookup"><span data-stu-id="550a5-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="550a5-114">Wykonanie funkcji zdalnej nie jest odzwierciedlone przez interfejs API profilera, więc powiadomienia o funkcjach, które są wywoływane z klienta i wykonywane na serwerze, nie są prawidłowo odbierane.</span><span class="sxs-lookup"><span data-stu-id="550a5-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="550a5-115">Rzeczywiste wywołanie odbywa się za pośrednictwem obiektu serwera proxy; do profilera pojawia się, że niektóre funkcje są skompilowane JIT, ale nigdy nie były używane.</span><span class="sxs-lookup"><span data-stu-id="550a5-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="550a5-116">Profiler nie odbiera dokładne powiadomienia o asynchronicznych zdarzeniach zdalnych.</span><span class="sxs-lookup"><span data-stu-id="550a5-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="550a5-117">Wymagania</span><span class="sxs-lookup"><span data-stu-id="550a5-117">Requirements</span></span>  

 <span data-ttu-id="550a5-118">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="550a5-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="550a5-119">**Nagłówek:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="550a5-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="550a5-120">**Biblioteka:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="550a5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="550a5-121">**.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="550a5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="550a5-122">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="550a5-122">See also</span></span>

- [<span data-ttu-id="550a5-123">ICorProfilerCallback — Interfejs</span><span class="sxs-lookup"><span data-stu-id="550a5-123">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
