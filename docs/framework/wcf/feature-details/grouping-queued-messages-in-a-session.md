---
title: Grupowanie komunikatów z obsługą kolejek w ramach sesji
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- queues [WCF]. grouping messages
ms.assetid: 63b23b36-261f-4c37-99a2-cc323cd72a1a
ms.openlocfilehash: 9ad3bd29535e14231d07b9e491e606f8349ca3ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290065"
---
# <a name="grouping-queued-messages-in-a-session"></a><span data-ttu-id="5b560-102">Grupowanie komunikatów z obsługą kolejek w ramach sesji</span><span class="sxs-lookup"><span data-stu-id="5b560-102">Grouping Queued Messages in a Session</span></span>

<span data-ttu-id="5b560-103">Windows Communication Foundation (WCF) to sesja, która umożliwia grupowanie zestawu powiązanych komunikatów w celu przetworzenia przez pojedynczą aplikację otrzymującą.</span><span class="sxs-lookup"><span data-stu-id="5b560-103">Windows Communication Foundation (WCF) provides a session that allows you to group a set of related messages together for processing by a single receiving application.</span></span> <span data-ttu-id="5b560-104">Komunikaty, które są częścią sesji, muszą być częścią tej samej transakcji.</span><span class="sxs-lookup"><span data-stu-id="5b560-104">Messages that are part of a session must be part of the same transaction.</span></span> <span data-ttu-id="5b560-105">Ponieważ wszystkie komunikaty są częścią tej samej transakcji, jeśli nie można przetworzyć jednego komunikatu, cała sesja jest wycofywana.</span><span class="sxs-lookup"><span data-stu-id="5b560-105">Because all messages are part of the same transaction, if one message fails to be processed the entire session is rolled back.</span></span> <span data-ttu-id="5b560-106">Sesje mają podobne zachowania w odniesieniu do nieutraconych kolejek i trujących kolejek.</span><span class="sxs-lookup"><span data-stu-id="5b560-106">Sessions have similar behaviors with regard to dead-letter queues and poison queues.</span></span> <span data-ttu-id="5b560-107">Właściwość Time to Live (TTL) ustawiona w powiązaniu w kolejce skonfigurowanym dla sesji jest stosowana do sesji jako całości.</span><span class="sxs-lookup"><span data-stu-id="5b560-107">The Time to Live (TTL) property set on a queued binding configured for sessions is applied to the session as a whole.</span></span> <span data-ttu-id="5b560-108">Jeśli tylko niektóre komunikaty w sesji są wysyłane przed upływem czasu wygaśnięcia, cała sesja zostanie umieszczona w kolejce utraconych wiadomości.</span><span class="sxs-lookup"><span data-stu-id="5b560-108">If only some of the messages in the session are sent before the TTL expires, the entire session is placed in the dead-letter queue.</span></span> <span data-ttu-id="5b560-109">Podobnie w przypadku niepowodzenia wysyłania komunikatów w sesji do aplikacji z kolejki aplikacji cała sesja zostanie umieszczona w kolejce trującej (jeśli jest dostępna).</span><span class="sxs-lookup"><span data-stu-id="5b560-109">Similarly, when messages in a session fail to be sent to an application from the application queue, the entire session is placed in the poison queue (if available).</span></span>  
  
## <a name="message-grouping-example"></a><span data-ttu-id="5b560-110">Przykład grupowania komunikatów</span><span class="sxs-lookup"><span data-stu-id="5b560-110">Message Grouping Example</span></span>  

 <span data-ttu-id="5b560-111">Przykładem, gdy pomocne jest grupowanie komunikatów, jest zaimplementowanie aplikacji do przetwarzania zamówień jako usługi WCF.</span><span class="sxs-lookup"><span data-stu-id="5b560-111">One example where grouping messages is helpful is when implementing an order-processing application as a WCF service.</span></span> <span data-ttu-id="5b560-112">Na przykład klient przesyła do tej aplikacji zamówienie, które zawiera kilka elementów.</span><span class="sxs-lookup"><span data-stu-id="5b560-112">For instance, a client submits an order to this application that contains a number of items.</span></span> <span data-ttu-id="5b560-113">Dla każdego elementu klient wykonuje wywołanie do usługi, co spowoduje wysłanie osobnej wiadomości.</span><span class="sxs-lookup"><span data-stu-id="5b560-113">For each item, the client makes a call to the service, which results in a separate message being sent.</span></span> <span data-ttu-id="5b560-114">Jest możliwe, aby program mógł otrzymać pierwszy element, a serwer B odbierze drugi element.</span><span class="sxs-lookup"><span data-stu-id="5b560-114">It is possible for serve A to receive the first item, and server B to receive the second item.</span></span> <span data-ttu-id="5b560-115">Za każdym razem, gdy element jest dodawany, serwer przetwarzania tego elementu musi znaleźć odpowiednie zamówienie i dodać do niego element, który jest wysoce nieefektywny.</span><span class="sxs-lookup"><span data-stu-id="5b560-115">Each time an item is added, the server processing that item has to find the appropriate order and add the item to it, which is highly inefficient.</span></span> <span data-ttu-id="5b560-116">W dalszym ciągu można pracować w taki sposób, że tylko jeden serwer obsługuje wszystkie żądania, ponieważ serwer musi śledzić wszystkie aktualnie przetwarzane zamówienia i określić, do którego, do którego należy nowy element.</span><span class="sxs-lookup"><span data-stu-id="5b560-116">You still run into such inefficiencies with only a single server handling all requests, because the server must keep track of all orders currently being processed and determine which one the new item belongs to.</span></span> <span data-ttu-id="5b560-117">Grupowanie wszystkich żądań dla pojedynczego zamówienia znacznie upraszcza implementację takiej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="5b560-117">Grouping all requests for a single order greatly simplifies implementation of such an application.</span></span> <span data-ttu-id="5b560-118">Aplikacja kliencka wysyła wszystkie elementy z pojedynczej kolejności w sesji, więc gdy usługa przetwarza kolejność, przetwarza całą sesję jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="5b560-118">The client application sends all items for a single order in a session, so when the service processes the order, it processes the entire session at once.</span></span> \  
  
## <a name="procedures"></a><span data-ttu-id="5b560-119">Procedury</span><span class="sxs-lookup"><span data-stu-id="5b560-119">Procedures</span></span>  
  
#### <a name="to-set-up-a-service-contract-to-use-sessions"></a><span data-ttu-id="5b560-120">Aby skonfigurować kontrakt usługi do korzystania z sesji</span><span class="sxs-lookup"><span data-stu-id="5b560-120">To set up a service contract to use sessions</span></span>  
  
1. <span data-ttu-id="5b560-121">Zdefiniuj kontrakt usługi wymagający sesji.</span><span class="sxs-lookup"><span data-stu-id="5b560-121">Define a service contract that requires a session.</span></span> <span data-ttu-id="5b560-122">Zrób to z <xref:System.ServiceModel.ServiceContractAttribute> atrybutem, określając:</span><span class="sxs-lookup"><span data-stu-id="5b560-122">Do this with the <xref:System.ServiceModel.ServiceContractAttribute> attribute by specifying:</span></span>  
  
    ```csharp
    SessionMode=SessionMode.Required  
    ```  
  
2. <span data-ttu-id="5b560-123">Oznacz operacje w kontrakcie jako jednokierunkowe, ponieważ te metody nie zwracają żadnych elementów.</span><span class="sxs-lookup"><span data-stu-id="5b560-123">Mark the operations in the contract as one-way, because these methods do not return anything.</span></span> <span data-ttu-id="5b560-124">Jest to wykonywane z <xref:System.ServiceModel.OperationContractAttribute> atrybutem, określając:</span><span class="sxs-lookup"><span data-stu-id="5b560-124">This is done with the <xref:System.ServiceModel.OperationContractAttribute> attribute by specifying:</span></span>  
  
    ```csharp  
    [OperationContract(IsOneWay = true)]  
    ```  
  
3. <span data-ttu-id="5b560-125">Zaimplementuj kontrakt usługi i określ <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode> <xref:System.ServiceModel.InstanceContextMode.PerSession?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="5b560-125">Implement the service contract and specify an <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode> of <xref:System.ServiceModel.InstanceContextMode.PerSession?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5b560-126">Spowoduje to utworzenie wystąpienia usługi tylko raz dla każdej sesji.</span><span class="sxs-lookup"><span data-stu-id="5b560-126">This instantiates the service only once for each session.</span></span>  
  
    ```csharp  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    ```  
  
4. <span data-ttu-id="5b560-127">Każda operacja usługi wymaga transakcji.</span><span class="sxs-lookup"><span data-stu-id="5b560-127">Each service operation requires a transaction.</span></span> <span data-ttu-id="5b560-128">Określ ten <xref:System.ServiceModel.OperationBehaviorAttribute> atrybut.</span><span class="sxs-lookup"><span data-stu-id="5b560-128">Specify this with the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span> <span data-ttu-id="5b560-129">Operacja, która kończy transakcję, powinna również mieć ustawioną wartość <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete> `true` .</span><span class="sxs-lookup"><span data-stu-id="5b560-129">The operation that completes the transaction should also set <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete> to `true`.</span></span>  
  
    ```csharp  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    ```  
  
5. <span data-ttu-id="5b560-130">Skonfiguruj punkt końcowy, który używa powiązania dostarczonego przez system `NetMsmqBinding` .</span><span class="sxs-lookup"><span data-stu-id="5b560-130">Configure an endpoint that uses the system-provided `NetMsmqBinding` binding.</span></span>  
  
6. <span data-ttu-id="5b560-131">Utwórz kolejkę transakcyjną przy użyciu <xref:System.Messaging> .</span><span class="sxs-lookup"><span data-stu-id="5b560-131">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="5b560-132">Możesz również utworzyć kolejkę za pomocą usługi kolejkowania komunikatów (MSMQ) lub MMC.</span><span class="sxs-lookup"><span data-stu-id="5b560-132">You can also create the queue by using Message Queuing (MSMQ) or MMC.</span></span> <span data-ttu-id="5b560-133">W takim przypadku należy utworzyć kolejkę transakcyjną.</span><span class="sxs-lookup"><span data-stu-id="5b560-133">If you do, create a transactional queue.</span></span>  
  
7. <span data-ttu-id="5b560-134">Utwórz hosta usługi dla usługi przy użyciu programu <xref:System.ServiceModel.ServiceHost> .</span><span class="sxs-lookup"><span data-stu-id="5b560-134">Create a service host for the service by using <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
8. <span data-ttu-id="5b560-135">Otwórz hosta usługi, aby udostępnić usługę.</span><span class="sxs-lookup"><span data-stu-id="5b560-135">Open the service host to make the service available.</span></span>  
  
9. <span data-ttu-id="5b560-136">Zamknij hosta usługi.</span><span class="sxs-lookup"><span data-stu-id="5b560-136">Close the service host.</span></span>  
  
#### <a name="to-set-up-a-client"></a><span data-ttu-id="5b560-137">Aby skonfigurować klienta</span><span class="sxs-lookup"><span data-stu-id="5b560-137">To set up a client</span></span>  
  
1. <span data-ttu-id="5b560-138">Utwórz zakres transakcji do zapisu w kolejce transakcyjnej.</span><span class="sxs-lookup"><span data-stu-id="5b560-138">Create a transaction scope to write to the transactional queue.</span></span>  
  
2. <span data-ttu-id="5b560-139">Utwórz klienta WCF przy użyciu narzędzia do [Zametadanych modelu ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) .</span><span class="sxs-lookup"><span data-stu-id="5b560-139">Create the WCF client using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) tool.</span></span>  
  
3. <span data-ttu-id="5b560-140">Złóż zamówienie.</span><span class="sxs-lookup"><span data-stu-id="5b560-140">Place the order.</span></span>  
  
4. <span data-ttu-id="5b560-141">Zamknij klienta WCF.</span><span class="sxs-lookup"><span data-stu-id="5b560-141">Close the WCF client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b560-142">Przykład</span><span class="sxs-lookup"><span data-stu-id="5b560-142">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="5b560-143">Opis</span><span class="sxs-lookup"><span data-stu-id="5b560-143">Description</span></span>  

 <span data-ttu-id="5b560-144">Poniższy przykład zawiera kod dla `IProcessOrder` usługi i klienta programu korzystającego z tej usługi.</span><span class="sxs-lookup"><span data-stu-id="5b560-144">The following example provides the code for the `IProcessOrder` service and for a client that uses this service.</span></span> <span data-ttu-id="5b560-145">Pokazuje, w jaki sposób WCF używa kolejkowane sesje, aby zapewnić zachowanie grupowania.</span><span class="sxs-lookup"><span data-stu-id="5b560-145">It shows how WCF uses queued sessions to provide the grouping behavior.</span></span>  
  
### <a name="code-for-the-service"></a><span data-ttu-id="5b560-146">Kod usługi</span><span class="sxs-lookup"><span data-stu-id="5b560-146">Code for the Service</span></span>  

 [!code-csharp[S_Msmq_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/service.cs#1)]
 [!code-vb[S_Msmq_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/service.vb#1)]  

### <a name="code-for-the-client"></a><span data-ttu-id="5b560-147">Kod dla klienta</span><span class="sxs-lookup"><span data-stu-id="5b560-147">Code for the Client</span></span>  

 [!code-csharp[S_Msmq_Session#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/client.cs#3)]
 [!code-vb[S_Msmq_Session#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/client.vb#3)]  

## <a name="see-also"></a><span data-ttu-id="5b560-148">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5b560-148">See also</span></span>

- [<span data-ttu-id="5b560-149">Sesje i kolejki</span><span class="sxs-lookup"><span data-stu-id="5b560-149">Sessions and Queues</span></span>](../samples/sessions-and-queues.md)
- [<span data-ttu-id="5b560-150">Omówienie kolejek</span><span class="sxs-lookup"><span data-stu-id="5b560-150">Queues Overview</span></span>](queues-overview.md)
