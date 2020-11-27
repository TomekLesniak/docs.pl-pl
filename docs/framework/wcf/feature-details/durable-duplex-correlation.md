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
# <a name="durable-duplex-correlation"></a>Niezawodna korelacja dwukierunkowa

Niezależna korelacja dupleksu, nazywana również korelacją wywołania zwrotnego, jest przydatna, gdy usługa przepływu pracy wymaga do wysłania wywołania zwrotnego do początkowego obiektu wywołującego. W przeciwieństwie do funkcji WCF, wywołanie zwrotne może wystąpić w dowolnym momencie w przyszłości i nie jest powiązane z tym samym kanałem lub okresem istnienia kanału. Jedynym wymaganiem jest, że obiekt wywołujący ma aktywny punkt końcowy nasłuchujący wiadomości wywołania zwrotnego. Dzięki temu dwie usługi przepływu pracy mogą komunikować się w długotrwałej konwersacji. Ten temat zawiera omówienie trwałej korelacji dupleksowej.  
  
## <a name="using-durable-duplex-correlation"></a>Używanie trwałej korelacji dupleksowej  

 Aby można było użyć korelacji z trwałym dupleksem, dwie usługi muszą używać powiązania z obsługą kontekstu, które obsługuje operacje dwukierunkowe, takie jak <xref:System.ServiceModel.NetTcpContextBinding> lub <xref:System.ServiceModel.WSHttpContextBinding> . Usługa wywołująca rejestruje <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> z odpowiednim powiązaniem na swoim kliencie <xref:System.ServiceModel.Endpoint> . Usługa odbierająca odbiera te dane w wywołaniu początkowym, a następnie używa ich samodzielnie <xref:System.ServiceModel.Endpoint> w <xref:System.ServiceModel.Activities.Send> działaniu, które wywołuje z powrotem do usługi wywołującej. W tym przykładzie dwie usługi komunikują się ze sobą. Pierwsza usługa wywołuje metodę dla drugiej usługi, a następnie czeka na odpowiedź. Druga usługa zna nazwę metody wywołania zwrotnego, ale punkt końcowy usługi implementującej tę metodę nie jest znany w czasie projektowania.  
  
> [!NOTE]
> Trwały dupleks można używać tylko wtedy, gdy <xref:System.ServiceModel.Channels.AddressingVersion> punkt końcowy jest skonfigurowany przy użyciu <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A> . Jeśli tak nie jest, <xref:System.InvalidOperationException> zostanie zgłoszony wyjątek z następującym komunikatem: "komunikat zawiera nagłówek kontekstu wywołania zwrotnego z odwołaniem do punktu końcowego dla [AddressingVersion](http://schemas.xmlsoap.org/ws/2004/08/addressing). Kontekst wywołania zwrotnego można przesłać tylko wtedy, gdy AddressingVersion jest skonfigurowany przy użyciu elementu "WSAddressing10".
  
 W poniższym przykładzie jest hostowana usługa przepływu pracy, która tworzy wywołanie zwrotne <xref:System.ServiceModel.Endpoint> przy użyciu <xref:System.ServiceModel.WSHttpContextBinding> .  
  
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
  
 Przepływ pracy implementujący tę usługę przepływu pracy inicjuje korelację wywołania zwrotnego z jego <xref:System.ServiceModel.Activities.Send> działaniem i odwołuje się do tego punktu końcowego wywołania zwrotnego z <xref:System.ServiceModel.Activities.Receive> działania, które jest skorelowane z <xref:System.ServiceModel.Activities.Send> . Poniższy przykład reprezentuje przepływ pracy, który jest zwracany przez `GetWF1` metodę.  
  
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
  
 Druga usługa przepływu pracy jest hostowana przy użyciu opartego na systemie powiązania.  
  
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
  
 Przepływ pracy implementujący tę usługę przepływu pracy rozpoczyna się od <xref:System.ServiceModel.Activities.Receive> działania. To działanie Receive inicjuje korelację wywołania zwrotnego dla tej usługi, opóźnia przez pewien czas, aby symulować długotrwałą pracę, a następnie wywołuje z powrotem do pierwszej usługi przy użyciu kontekstu wywołania zwrotnego, który został przesłany podczas pierwszego wywołania usługi. Poniższy przykład reprezentuje przepływ pracy, który jest zwracany z wywołania do `GetWF2` . Należy pamiętać, że <xref:System.ServiceModel.Activities.Send> działanie ma symbol zastępczy `http://www.contoso.com` ; rzeczywisty adres używany w czasie wykonywania jest adresem określonego wywołania zwrotnego.  
  
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
  
 Gdy `StartOrder` Metoda jest wywoływana w pierwszym przepływie pracy, wyświetlane są następujące dane wyjściowe, które pokazują przepływ wykonywania przez dwa przepływy pracy.  
  
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
  
 W tym przykładzie oba przepływy pracy jawnie zarządzają korelacją przy użyciu <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer> . Ponieważ w tych przykładowych przepływach pracy istniała tylko jedna korelacja, domyślne <xref:System.ServiceModel.Activities.CorrelationHandle> Zarządzanie byłoby wystarczające.
