---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 69da35f65e04a3cba15885c4fe6e57d63762cb1c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260347"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="7049d-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="7049d-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>

<span data-ttu-id="7049d-103">Skażony komunikat został odrzucony.</span><span class="sxs-lookup"><span data-stu-id="7049d-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7049d-104">Opis</span><span class="sxs-lookup"><span data-stu-id="7049d-104">Description</span></span>  

 <span data-ttu-id="7049d-105">Ślad wskazuje, że napotkano trującą wiadomość, a następnie odrzucono ją.</span><span class="sxs-lookup"><span data-stu-id="7049d-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="7049d-106">Dzieje się tak, gdy `ReceiveErrorHandling` Właściwość w usłudze msmqbinding lub MsmqIntegrationBinding jest ustawiona na wartość `Reject` .</span><span class="sxs-lookup"><span data-stu-id="7049d-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="7049d-107">Odrzucony komunikat jest dostarczany z powrotem do [kolejki utraconych wiadomości](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)nadawcy.</span><span class="sxs-lookup"><span data-stu-id="7049d-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="7049d-108">Aby uzyskać więcej informacji na temat sytuacji, w których komunikaty stają się trujące i jak skonfigurować usługę do odpowiednich potrzeb, zobacz [Obsługa komunikatów trujących](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="7049d-108">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="7049d-109">Aby uzyskać więcej informacji na temat tego, co oznacza komunikat odrzucony w usłudze MSMQ, zobacz [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="7049d-109">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7049d-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7049d-110">See also</span></span>

- [<span data-ttu-id="7049d-111">Śledzenie</span><span class="sxs-lookup"><span data-stu-id="7049d-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="7049d-112">Rozwiązywanie problemów z aplikacją za pomocą śledzenia</span><span class="sxs-lookup"><span data-stu-id="7049d-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="7049d-113">Administracja i Diagnostyka</span><span class="sxs-lookup"><span data-stu-id="7049d-113">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="7049d-114">Obsługa komunikatów trujących</span><span class="sxs-lookup"><span data-stu-id="7049d-114">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="7049d-115">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="7049d-115">[MQMarkMessageRejected](/previous-versions/windows/desktop/msmq/ms707071(v=vs.85))</span></span>
