---
title: Przetwarzanie komunikatów poza kolejnością
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 7a5042e390231498de4f98abfc0e863cba199943
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248008"
---
# <a name="out-of-order-message-processing"></a><span data-ttu-id="867f6-102">Przetwarzanie komunikatów poza kolejnością</span><span class="sxs-lookup"><span data-stu-id="867f6-102">Out-of-Order Message Processing</span></span>

<span data-ttu-id="867f6-103">Usługi przepływu pracy mogą zależeć od komunikatów wysyłanych w określonej kolejności.</span><span class="sxs-lookup"><span data-stu-id="867f6-103">Workflow services may depend on messages being sent in a specific order.</span></span> <span data-ttu-id="867f6-104">Usługa przepływu pracy zawiera co najmniej jedną <xref:System.ServiceModel.Activities.Receive> czynność, a każde <xref:System.ServiceModel.Activities.Receive> działanie oczekuje określonego komunikatu.</span><span class="sxs-lookup"><span data-stu-id="867f6-104">A workflow service contains one or more <xref:System.ServiceModel.Activities.Receive> activities and each <xref:System.ServiceModel.Activities.Receive> activity is expecting a specific message.</span></span> <span data-ttu-id="867f6-105">Bez określonych gwarancji dostarczania transportowego komunikaty wysyłane przez klientów mogą być opóźnione i w związku z tym dostarczane w kolejności, w której usługa przepływu pracy może się nie spodziewać.</span><span class="sxs-lookup"><span data-stu-id="867f6-105">Without particular transport delivery guarantees, messages sent by clients may be delayed and therefore delivered in an order the workflow service may not expect.</span></span> <span data-ttu-id="867f6-106">Implementacja usługi przepływu pracy, która nie wymaga przesyłania komunikatów w określonej kolejności, zwykle odbywa się przy użyciu działania równoległego.</span><span class="sxs-lookup"><span data-stu-id="867f6-106">Implementing a workflow service that does not require messages be sent in a specific order is normally done using a Parallel activity.</span></span> <span data-ttu-id="867f6-107">W przypadku bardziej skomplikowanego protokołu aplikacji przepływ pracy staje się bardzo skomplikowany bardzo szybko.</span><span class="sxs-lookup"><span data-stu-id="867f6-107">For a more complicated application protocol, the workflow would become very complex very quickly.</span></span>  <span data-ttu-id="867f6-108">Funkcja przetwarzania komunikatów poza kolejnością w programie Windows Communication Foundation (WCF) umożliwia tworzenie takiego przepływu pracy bez żadnej złożoności zagnieżdżonych działań równoległych.</span><span class="sxs-lookup"><span data-stu-id="867f6-108">The out-of-order message processing feature in Windows Communication Foundation (WCF) allows you to create such a workflow without all of the complexity of nested Parallel activities.</span></span> <span data-ttu-id="867f6-109">Przetwarzanie komunikatów poza kolejnością jest obsługiwane tylko w przypadku kanałów obsługujących <xref:System.ServiceModel.Channels.ReceiveContext> takie działania jak powiązania MSMQ usługi WCF.</span><span class="sxs-lookup"><span data-stu-id="867f6-109">Out-of-order message processing is only supported on channels that support <xref:System.ServiceModel.Channels.ReceiveContext> such as the WCF MSMQ bindings.</span></span>  
  
## <a name="enabling-out-of-order-message-processing"></a><span data-ttu-id="867f6-110">Włączanie przetwarzania komunikatów poza kolejnością</span><span class="sxs-lookup"><span data-stu-id="867f6-110">Enabling Out-Of-Order Message Processing</span></span>  

 <span data-ttu-id="867f6-111">Przetwarzanie komunikatów poza kolejnością jest włączane przez ustawienie właściwości na <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> `true` obiektu WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="867f6-111">Out-of-order message processing is enabled by setting the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property to `true` on the WorkflowService.</span></span> <span data-ttu-id="867f6-112">Poniższy przykład pokazuje, jak ustawić <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> Właściwość w kodzie.</span><span class="sxs-lookup"><span data-stu-id="867f6-112">The following example shows how to set the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property in code.</span></span>  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 <span data-ttu-id="867f6-113">Można również zastosować `AllowBufferedReceive` atrybut do usługi przepływu pracy w języku XAML, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="867f6-113">You can also apply the `AllowBufferedReceive` attribute to a workflow service in XAML as shown in the following example.</span></span>  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a><span data-ttu-id="867f6-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="867f6-114">See also</span></span>

- <xref:System.ServiceModel.Channels.ReceiveContext>
- [<span data-ttu-id="867f6-115">Usługi przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="867f6-115">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="867f6-116">Kolejki i sesje niezawodne</span><span class="sxs-lookup"><span data-stu-id="867f6-116">Queues and Reliable Sessions</span></span>](queues-and-reliable-sessions.md)
