---
title: Niezawodna korelacja dwukierunkowa
ms.date: 03/30/2017
ms.assetid: 8eb0e49a-6d3b-4f7e-a054-0d4febee2ffb
ms.openlocfilehash: eb879c583b4454cd0062396d86e157a90db4652f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254236"
---
# <a name="durable-duplex-correlation"></a><span data-ttu-id="50a49-102">Niezawodna korelacja dwukierunkowa</span><span class="sxs-lookup"><span data-stu-id="50a49-102">Durable Duplex Correlation</span></span>

<span data-ttu-id="50a49-103">Niezależna korelacja dupleksu, nazywana również korelacją wywołania zwrotnego, jest przydatna, gdy usługa przepływu pracy wymaga do wysłania wywołania zwrotnego do początkowego obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="50a49-103">Durable duplex correlation, also known as callback correlation, is useful when a workflow service has a requirement to send a callback to the initial caller.</span></span> <span data-ttu-id="50a49-104">W przeciwieństwie do funkcji WCF, wywołanie zwrotne może wystąpić w dowolnym momencie w przyszłości i nie jest powiązane z tym samym kanałem lub okresem istnienia kanału. Jedynym wymaganiem jest, że obiekt wywołujący ma aktywny punkt końcowy nasłuchujący wiadomości wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="50a49-104">Unlike WCF duplex, the callback can happen at any time in the future and is not tied to the same channel or the channel lifetime; the only requirement is that the caller have an active endpoint listening for the callback message.</span></span> <span data-ttu-id="50a49-105">Dzięki temu dwie usługi przepływu pracy mogą komunikować się w długotrwałej konwersacji.</span><span class="sxs-lookup"><span data-stu-id="50a49-105">This allows two workflow services to communicate in a long-running conversation.</span></span> <span data-ttu-id="50a49-106">Ten temat zawiera omówienie trwałej korelacji dupleksowej.</span><span class="sxs-lookup"><span data-stu-id="50a49-106">This topic provides an overview of durable duplex correlation.</span></span>  
  
## <a name="using-durable-duplex-correlation"></a><span data-ttu-id="50a49-107">Używanie trwałej korelacji dupleksowej</span><span class="sxs-lookup"><span data-stu-id="50a49-107">Using Durable Duplex Correlation</span></span>  

 <span data-ttu-id="50a49-108">Aby można było użyć korelacji z trwałym dupleksem, dwie usługi muszą używać powiązania z obsługą kontekstu, które obsługuje operacje dwukierunkowe, takie jak <xref:System.ServiceModel.NetTcpContextBinding> lub <xref:System.ServiceModel.WSHttpContextBinding> .</span><span class="sxs-lookup"><span data-stu-id="50a49-108">To use durable duplex correlation, the two services must use a context-enabled binding that supports two-way operations, such as <xref:System.ServiceModel.NetTcpContextBinding> or <xref:System.ServiceModel.WSHttpContextBinding>.</span></span> <span data-ttu-id="50a49-109">Usługa wywołująca rejestruje <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> z odpowiednim powiązaniem na swoim kliencie <xref:System.ServiceModel.Endpoint> .</span><span class="sxs-lookup"><span data-stu-id="50a49-109">The calling service registers a <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> with the desired binding on their client <xref:System.ServiceModel.Endpoint>.</span></span> <span data-ttu-id="50a49-110">Usługa odbierająca odbiera te dane w wywołaniu początkowym, a następnie używa ich samodzielnie <xref:System.ServiceModel.Endpoint> w <xref:System.ServiceModel.Activities.Send> działaniu, które wywołuje z powrotem do usługi wywołującej.</span><span class="sxs-lookup"><span data-stu-id="50a49-110">The receiving service receives this data in the initial call and then uses it on its own <xref:System.ServiceModel.Endpoint> in the <xref:System.ServiceModel.Activities.Send> activity that makes the call back to the calling service.</span></span> <span data-ttu-id="50a49-111">W tym przykładzie dwie usługi komunikują się ze sobą.</span><span class="sxs-lookup"><span data-stu-id="50a49-111">In this example, two services communicate with each other.</span></span> <span data-ttu-id="50a49-112">Pierwsza usługa wywołuje metodę dla drugiej usługi, a następnie czeka na odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="50a49-112">The first service invokes a method on the second service and then waits for a reply.</span></span> <span data-ttu-id="50a49-113">Druga usługa zna nazwę metody wywołania zwrotnego, ale punkt końcowy usługi implementującej tę metodę nie jest znany w czasie projektowania.</span><span class="sxs-lookup"><span data-stu-id="50a49-113">The second service knows the name of the callback method, but the endpoint of the service that implements this method is not known at design time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50a49-114">Trwały dupleks można używać tylko wtedy, gdy <xref:System.ServiceModel.Channels.AddressingVersion> punkt końcowy jest skonfigurowany przy użyciu <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A> .</span><span class="sxs-lookup"><span data-stu-id="50a49-114">Durable duplex can only be used when the <xref:System.ServiceModel.Channels.AddressingVersion> of the endpoint is configured with <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A>.</span></span> <span data-ttu-id="50a49-115">Jeśli tak nie jest, <xref:System.InvalidOperationException> zostanie zgłoszony wyjątek z następującym komunikatem: "komunikat zawiera nagłówek kontekstu wywołania zwrotnego z odwołaniem do punktu końcowego dla [AddressingVersion](http://schemas.xmlsoap.org/ws/2004/08/addressing).</span><span class="sxs-lookup"><span data-stu-id="50a49-115">If it is not, then an <xref:System.InvalidOperationException> exception is thrown with the following message: "The message contains a callback context header with an endpoint reference for [AddressingVersion](http://schemas.xmlsoap.org/ws/2004/08/addressing).</span></span> <span data-ttu-id="50a49-116">Kontekst wywołania zwrotnego można przesłać tylko wtedy, gdy AddressingVersion jest skonfigurowany przy użyciu elementu "WSAddressing10".</span><span class="sxs-lookup"><span data-stu-id="50a49-116">Callback context can only be transmitted when the AddressingVersion is configured with 'WSAddressing10'.</span></span>
  
 <span data-ttu-id="50a49-117">W poniższym przykładzie jest hostowana usługa przepływu pracy, która tworzy wywołanie zwrotne <xref:System.ServiceModel.Endpoint> przy użyciu <xref:System.ServiceModel.WSHttpContextBinding> .</span><span class="sxs-lookup"><span data-stu-id="50a49-117">In the following example, a workflow service is hosted that creates a callback <xref:System.ServiceModel.Endpoint> using <xref:System.ServiceModel.WSHttpContextBinding>.</span></span>  
  
```csharp  
// Host WF Service 1.  
string baseAddress1 = "http://localhost:8080/Service1";  
WorkflowServiceHost host1 = new WorkflowServiceHost(GetWF1(), new Uri(baseAddress1));  
  
// Add the callback endpoint.  
WSHttpContextBinding Binding1 = new WSHttpContextBinding();  
host1.AddServiceEndpoint("ICallbackItemsReady", Binding1, "ItemsReady");  
  
// Add the service endpoint.  
host1.AddServiceEndpoint("IService1", Binding1, baseAddress1);  
  
// Open the first workflow service.  
host1.Open();  
Console.WriteLine("Service1 waiting at: {0}", baseAddress1);  
```  
  
 <span data-ttu-id="50a49-118">Przepływ pracy implementujący tę usługę przepływu pracy inicjuje korelację wywołania zwrotnego z jego <xref:System.ServiceModel.Activities.Send> działaniem i odwołuje się do tego punktu końcowego wywołania zwrotnego z <xref:System.ServiceModel.Activities.Receive> działania, które jest skorelowane z <xref:System.ServiceModel.Activities.Send> .</span><span class="sxs-lookup"><span data-stu-id="50a49-118">The workflow that implements this workflow service initializes the callback correlation with its <xref:System.ServiceModel.Activities.Send> activity, and references this callback endpoint from the <xref:System.ServiceModel.Activities.Receive> activity that correlates with the <xref:System.ServiceModel.Activities.Send>.</span></span> <span data-ttu-id="50a49-119">Poniższy przykład reprezentuje przepływ pracy, który jest zwracany przez `GetWF1` metodę.</span><span class="sxs-lookup"><span data-stu-id="50a49-119">The following example represents the workflow that is returned from the `GetWF1` method.</span></span>  
  
```csharp  
Variable<CorrelationHandle> CallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IService1",  
    OperationName = "StartOrder"  
};  
  
Send GetItems = new Send  
{  
    CorrelationInitializers =
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = CallbackHandle  
        }  
    },  
    ServiceContractName = "IService2",  
    OperationName = "StartItems",  
    Endpoint = new Endpoint  
    {  
        AddressUri = new Uri("http://localhost:8081/Service2"),  
        Binding = new WSHttpContextBinding  
        {  
            ClientCallbackAddress = new Uri("http://localhost:8080/Service1/ItemsReady")
        }  
    }  
};  
  
Receive ItemsReady = new Receive  
{  
    ServiceContractName = "ICallbackItemsReady",  
    OperationName = "ItemsReady",  
    CorrelatesWith = CallbackHandle,  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        CallbackHandle  
    },  
    Activities =  
    {  
        StartOrder,  
        new WriteLine  
        {  
            Text = "WF1 - Started"  
        },  
        GetItems,  
        new WriteLine  
        {  
            Text = "WF1 - Request Submitted"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF1 - Items Received"  
        }  
     }  
};  
```  
  
 <span data-ttu-id="50a49-120">Druga usługa przepływu pracy jest hostowana przy użyciu opartego na systemie powiązania.</span><span class="sxs-lookup"><span data-stu-id="50a49-120">The second workflow service is hosted using a system-provided, context-based binding.</span></span>  
  
```csharp  
// Host WF Service 2.  
string baseAddress2 = "http://localhost:8081/Service2";  
WorkflowServiceHost host2 = new WorkflowServiceHost(GetWF2(), new Uri(baseAddress2));  
  
// Add the service endpoint.  
WSHttpContextBinding Binding2 = new WSHttpContextBinding();  
host2.AddServiceEndpoint("IService2", Binding2, baseAddress2);  
  
// Open the second workflow service.  
host2.Open();  
Console.WriteLine("Service2 waiting at: {0}", baseAddress2);  
```  
  
 <span data-ttu-id="50a49-121">Przepływ pracy implementujący tę usługę przepływu pracy rozpoczyna się od <xref:System.ServiceModel.Activities.Receive> działania.</span><span class="sxs-lookup"><span data-stu-id="50a49-121">The workflow that implements this workflow service begins with a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="50a49-122">To działanie Receive inicjuje korelację wywołania zwrotnego dla tej usługi, opóźnia przez pewien czas, aby symulować długotrwałą pracę, a następnie wywołuje z powrotem do pierwszej usługi przy użyciu kontekstu wywołania zwrotnego, który został przesłany podczas pierwszego wywołania usługi.</span><span class="sxs-lookup"><span data-stu-id="50a49-122">This receive activity initializes the callback correlation for this service, delays for a period of time to simulate long-running work, and then calls back into the first service using the callback context that was passed in the first call into the service.</span></span> <span data-ttu-id="50a49-123">Poniższy przykład reprezentuje przepływ pracy, który jest zwracany z wywołania do `GetWF2` .</span><span class="sxs-lookup"><span data-stu-id="50a49-123">The following example represents the workflow that is returned from a call to `GetWF2`.</span></span> <span data-ttu-id="50a49-124">Należy pamiętać, że <xref:System.ServiceModel.Activities.Send> działanie ma symbol zastępczy `http://www.contoso.com` ; rzeczywisty adres używany w czasie wykonywania jest adresem określonego wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="50a49-124">Note that the <xref:System.ServiceModel.Activities.Send> activity has a placeholder address of `http://www.contoso.com`; the actual address used at runtime is the supplied callback address.</span></span>  
  
```csharp  
Variable<CorrelationHandle> ItemsCallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartItems = new Receive  
{  
    CorrelationInitializers =
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = ItemsCallbackHandle  
        }  
    },  
    CanCreateInstance = true,  
    ServiceContractName = "IService2",  
    OperationName = "StartItems"  
};  
  
Send ItemsReady = new Send  
{  
    CorrelatesWith = ItemsCallbackHandle,  
    Endpoint = new Endpoint  
    {  
        // The callback address on the binding is used  
        // instead of this placeholder address.  
        AddressUri = new Uri("http://www.contoso.com"),  
  
        Binding = new WSHttpContextBinding()  
    },  
    OperationName = "ItemsReady",  
    ServiceContractName = "ICallbackItemsReady"  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        ItemsCallbackHandle  
    },  
    Activities =  
    {  
        StartItems,  
        new WriteLine  
        {  
            Text = "WF2 - Request Received"  
        },  
        new Delay  
        {  
            Duration = TimeSpan.FromMinutes(90)  
        },  
        new WriteLine  
        {  
            Text = "WF2 - Sending items"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF2 - Items sent"  
        }  
     }  
};  
```  
  
 <span data-ttu-id="50a49-125">Gdy `StartOrder` Metoda jest wywoływana w pierwszym przepływie pracy, wyświetlane są następujące dane wyjściowe, które pokazują przepływ wykonywania przez dwa przepływy pracy.</span><span class="sxs-lookup"><span data-stu-id="50a49-125">When the `StartOrder` method is invoked on the first workflow, the following output is displayed, which shows the flow of execution through the two workflows.</span></span>  
  
```output  
Service1 waiting at: http://localhost:8080/Service1  
Service2 waiting at: http://localhost:8081/Service2  
Press enter to exit.
WF1 - Started  
WF2 - Request Received  
WF1 - Request Submitted  
WF2 - Sending items  
WF2 - Items sent  
WF1 - Items Received  
```  
  
 <span data-ttu-id="50a49-126">W tym przykładzie oba przepływy pracy jawnie zarządzają korelacją przy użyciu <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer> .</span><span class="sxs-lookup"><span data-stu-id="50a49-126">In this example, both workflows explicitly manage correlation using a <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>.</span></span> <span data-ttu-id="50a49-127">Ponieważ w tych przykładowych przepływach pracy istniała tylko jedna korelacja, domyślne <xref:System.ServiceModel.Activities.CorrelationHandle> Zarządzanie byłoby wystarczające.</span><span class="sxs-lookup"><span data-stu-id="50a49-127">Because there was only a single correlation in these sample workflows, the default <xref:System.ServiceModel.Activities.CorrelationHandle> management would have been sufficient.</span></span>
