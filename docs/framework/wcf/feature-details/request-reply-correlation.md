---
title: Korelacja żądań i odpowiedzi
ms.date: 03/30/2017
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
ms.openlocfilehash: da7739af7368cd7ebb55ed0ea2511e10f0bcb3f5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239071"
---
# <a name="request-reply-correlation"></a>Korelacja żądań i odpowiedzi

Korelacja typu żądanie-odpowiedź jest używana z <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> parą do implementowania operacji dwukierunkowej w usłudze przepływu pracy i z <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> parą, która wywołuje operację dwukierunkową w innej usłudze sieci Web. W przypadku wywoływania operacji dwukierunkowych w usłudze WCF usługa może być tradycyjnie bezwzględną, opartą na kodzie Windows Communication Foundation lub usługą przepływu pracy. Aby można było użyć korelacji typu żądanie-odpowiedź, należy użyć powiązania dwukierunkowego, takiego jak <xref:System.ServiceModel.BasicHttpBinding> . Bez względu na to, czy wywoływanie lub implementacja operacji dwukierunkowych, kroki inicjowania korelacji są podobne i zostały omówione w tej sekcji.  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a>Używanie korelacji w operacji Two-Way z opcją Receive/SendReply  

 <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> Para służy do implementowania operacji dwukierunkowej w usłudze przepływu pracy. Środowisko uruchomieniowe używa korelacji żądanie-odpowiedź, aby upewnić się, że odpowiedź jest wysyłana do poprawnego obiektu wywołującego. Gdy przepływ pracy jest hostowany przy użyciu <xref:System.ServiceModel.Activities.WorkflowServiceHost> , który jest przeznaczony dla usług przepływu pracy, to domyślne inicjowanie korelacji jest wystarczające. W tym scenariuszu <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> jest używana para dla przepływu pracy i nie jest wymagana żadna konkretna konfiguracja korelacji.  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
### <a name="explicitly-initializing-request-reply-correlation"></a>Jawne inicjowanie korelacji Request-Reply  

 Jeśli inne operacje dwukierunkowe są równolegle, należy jawnie skonfigurować korelację. Można to zrobić przez określenie <xref:System.ServiceModel.Activities.CorrelationHandle> i <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> lub umieszczenie <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> wewnątrz <xref:System.ServiceModel.Activities.CorrelationScope> . W tym przykładzie korelacja typu żądanie-odpowiedź jest konfigurowana dla <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> pary.  
  
```csharp  
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder",  
    CorrelationInitializers =  
    {  
        new RequestReplyCorrelationInitializer  
        {  
            CorrelationHandle = RRHandle  
        }  
    }  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
 Zamiast jawnie skonfigurować korelację, <xref:System.ServiceModel.Activities.CorrelationScope> można użyć działania. <xref:System.ServiceModel.Activities.CorrelationScope> zapewnia niejawną <xref:System.ServiceModel.Activities.CorrelationHandle> obsługę komunikatów, które zawiera. W tym przykładzie <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> para jest zawarta w <xref:System.ServiceModel.Activities.CorrelationScope> . Nie jest wymagana jawna konfiguracja korelacji.  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
CorrelationScope s = new CorrelationScope  
{  
    Body = new Sequence  
    {  
        Activities =
        {  
            StartOrder,  
            // Activities that create the reply.  
            ReplyToStartOrder  
        }  
    }  
};  
  
// Construct a workflow using the CorrelationScope.  
```  
  
 Jeśli wymagane są dodatkowe korelacje, można je skonfigurować przy użyciu <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> właściwości odpowiednich działań związanych z obsługą komunikatów przy użyciu żądanych `CorrelationInitializer` typów.  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a>Używanie korelacji w operacji Two-Way przy użyciu polecenia Send/ReceiveReply  

 <xref:System.ServiceModel.Activities.Receive>Działanie może być używane tylko w usłudze przepływu pracy hostowanej przez <xref:System.ServiceModel.Activities.WorkflowServiceHost> , <xref:System.ServiceModel.Activities.Send> a <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> para może być używana w dowolnym przepływie pracy, który musi wywołać metodę w usłudze sieci Web. Jeśli przepływ pracy jest hostowany przy użyciu <xref:System.ServiceModel.Activities.WorkflowServiceHost> , a następnie domyślna korelacja opisana w poprzedniej sekcji ma zastosowanie, ale jeśli nie, należy jawnie skonfigurować korelację przy użyciu pożądanych <xref:System.ServiceModel.Activities.CorrelationInitializer> i <xref:System.ServiceModel.Activities.CorrelationHandle> lub za pomocą niejawnego zarządzania uchwytami <xref:System.ServiceModel.Activities.CorrelationScope> .  
  
 W przypadku korzystania z **Dodaj odwołanie do usługi** w usłudze z operacjami dwukierunkowymi generowane są działania, które umożliwiają wewnętrznie Zawijanie <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> aktywności pary przy użyciu jawnie określonego korelacji żądania/odpowiedzi.
