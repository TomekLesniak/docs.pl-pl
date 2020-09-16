---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: c5401bae1d8e7f61939d8de321353f59f412f966
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535336"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="3a3e5-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="3a3e5-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="3a3e5-103">Skażony komunikat został odrzucony.</span><span class="sxs-lookup"><span data-stu-id="3a3e5-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3a3e5-104">Opis</span><span class="sxs-lookup"><span data-stu-id="3a3e5-104">Description</span></span>  

 <span data-ttu-id="3a3e5-105">Ślad wskazuje, że napotkano trującą wiadomość, a następnie odrzucono ją.</span><span class="sxs-lookup"><span data-stu-id="3a3e5-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="3a3e5-106">Dzieje się tak, gdy `ReceiveErrorHandling` Właściwość w usłudze msmqbinding lub MsmqIntegrationBinding jest ustawiona na wartość `Reject` .</span><span class="sxs-lookup"><span data-stu-id="3a3e5-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="3a3e5-107">Odrzucony komunikat jest dostarczany z powrotem do [kolejki utraconych wiadomości](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)nadawcy.</span><span class="sxs-lookup"><span data-stu-id="3a3e5-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="3a3e5-108">Aby uzyskać więcej informacji na temat sytuacji, w których komunikaty stają się trujące i jak skonfigurować usługę do odpowiednich potrzeb, zobacz [Obsługa komunikatów trujących](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="3a3e5-108">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="3a3e5-109">Aby uzyskać więcej informacji na temat tego, co oznacza komunikat odrzucony w usłudze MSMQ, zobacz [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="3a3e5-109">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a3e5-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3a3e5-110">See also</span></span>

- [<span data-ttu-id="3a3e5-111">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="3a3e5-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="3a3e5-112">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="3a3e5-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3a3e5-113">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="3a3e5-113">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="3a3e5-114">Obsługa komunikatów trujących</span><span class="sxs-lookup"><span data-stu-id="3a3e5-114">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="3a3e5-115">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="3a3e5-115">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span></span>
