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
# <a name="request-reply-correlation"></a><span data-ttu-id="1e5b0-102">Korelacja żądań i odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="1e5b0-102">Request-Reply Correlation</span></span>

<span data-ttu-id="1e5b0-103">Korelacja typu żądanie-odpowiedź jest używana z <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> parą do implementowania operacji dwukierunkowej w usłudze przepływu pracy i z <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> parą, która wywołuje operację dwukierunkową w innej usłudze sieci Web.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-103">Request-reply correlation is used with a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair to implement a two-way operation in a workflow service and with a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that invokes a two-way operation in another Web service.</span></span> <span data-ttu-id="1e5b0-104">W przypadku wywoływania operacji dwukierunkowych w usłudze WCF usługa może być tradycyjnie bezwzględną, opartą na kodzie Windows Communication Foundation lub usługą przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-104">When invoking a two-way operation in a WCF service, the service can be either a traditional imperative code-based Windows Communication Foundation (WCF) service or it can be a workflow service.</span></span> <span data-ttu-id="1e5b0-105">Aby można było użyć korelacji typu żądanie-odpowiedź, należy użyć powiązania dwukierunkowego, takiego jak <xref:System.ServiceModel.BasicHttpBinding> .</span><span class="sxs-lookup"><span data-stu-id="1e5b0-105">To use request-reply correlation a two-way binding must be used, such as <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="1e5b0-106">Bez względu na to, czy wywoływanie lub implementacja operacji dwukierunkowych, kroki inicjowania korelacji są podobne i zostały omówione w tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-106">Whether invoking or implementing a two-way operation, the correlation initialization steps are similar and are covered in this section.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a><span data-ttu-id="1e5b0-107">Używanie korelacji w operacji Two-Way z opcją Receive/SendReply</span><span class="sxs-lookup"><span data-stu-id="1e5b0-107">Using Correlation in a Two-Way Operation with Receive/SendReply</span></span>  

 <span data-ttu-id="1e5b0-108"><xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> Para służy do implementowania operacji dwukierunkowej w usłudze przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-108">A <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used to implement a two-way operation in a workflow service.</span></span> <span data-ttu-id="1e5b0-109">Środowisko uruchomieniowe używa korelacji żądanie-odpowiedź, aby upewnić się, że odpowiedź jest wysyłana do poprawnego obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-109">The runtime uses request-reply correlation to ensure that the reply is dispatched to the correct caller.</span></span> <span data-ttu-id="1e5b0-110">Gdy przepływ pracy jest hostowany przy użyciu <xref:System.ServiceModel.Activities.WorkflowServiceHost> , który jest przeznaczony dla usług przepływu pracy, to domyślne inicjowanie korelacji jest wystarczające.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-110">When a workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, which is the case for workflow services, then the default correlation initialization is sufficient.</span></span> <span data-ttu-id="1e5b0-111">W tym scenariuszu <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> jest używana para dla przepływu pracy i nie jest wymagana żadna konkretna konfiguracja korelacji.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-111">In this scenario, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used by a workflow, and no specific correlation configuration is required.</span></span>  
  
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
  
### <a name="explicitly-initializing-request-reply-correlation"></a><span data-ttu-id="1e5b0-112">Jawne inicjowanie korelacji Request-Reply</span><span class="sxs-lookup"><span data-stu-id="1e5b0-112">Explicitly Initializing Request-Reply Correlation</span></span>  

 <span data-ttu-id="1e5b0-113">Jeśli inne operacje dwukierunkowe są równolegle, należy jawnie skonfigurować korelację.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-113">If other two-way operations are in parallel, then correlation should be explicitly configured.</span></span> <span data-ttu-id="1e5b0-114">Można to zrobić przez określenie <xref:System.ServiceModel.Activities.CorrelationHandle> i <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> lub umieszczenie <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> wewnątrz <xref:System.ServiceModel.Activities.CorrelationScope> .</span><span class="sxs-lookup"><span data-stu-id="1e5b0-114">This can be done by specifying a <xref:System.ServiceModel.Activities.CorrelationHandle> and <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, or by placing the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> inside of a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="1e5b0-115">W tym przykładzie korelacja typu żądanie-odpowiedź jest konfigurowana dla <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> pary.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-115">In this example, request-reply correlation is configured on a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair.</span></span>  
  
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
  
 <span data-ttu-id="1e5b0-116">Zamiast jawnie skonfigurować korelację, <xref:System.ServiceModel.Activities.CorrelationScope> można użyć działania.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-116">Instead of explicitly configuring the correlation, a <xref:System.ServiceModel.Activities.CorrelationScope> activity can be used.</span></span> <span data-ttu-id="1e5b0-117"><xref:System.ServiceModel.Activities.CorrelationScope> zapewnia niejawną <xref:System.ServiceModel.Activities.CorrelationHandle> obsługę komunikatów, które zawiera.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-117"><xref:System.ServiceModel.Activities.CorrelationScope> provides an implicit <xref:System.ServiceModel.Activities.CorrelationHandle> to the messaging activities that it contains.</span></span> <span data-ttu-id="1e5b0-118">W tym przykładzie <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> para jest zawarta w <xref:System.ServiceModel.Activities.CorrelationScope> .</span><span class="sxs-lookup"><span data-stu-id="1e5b0-118">In this example, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is contained inside a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="1e5b0-119">Nie jest wymagana jawna konfiguracja korelacji.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-119">No explicit correlation configuration is required.</span></span>  
  
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
  
 <span data-ttu-id="1e5b0-120">Jeśli wymagane są dodatkowe korelacje, można je skonfigurować przy użyciu <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> właściwości odpowiednich działań związanych z obsługą komunikatów przy użyciu żądanych `CorrelationInitializer` typów.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-120">If additional correlations are required then they can be configured using the <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> property of the respective messaging activities using the desired `CorrelationInitializer` types.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a><span data-ttu-id="1e5b0-121">Używanie korelacji w operacji Two-Way przy użyciu polecenia Send/ReceiveReply</span><span class="sxs-lookup"><span data-stu-id="1e5b0-121">Using Correlation in a Two-Way Operation with Send/ReceiveReply</span></span>  

 <span data-ttu-id="1e5b0-122"><xref:System.ServiceModel.Activities.Receive>Działanie może być używane tylko w usłudze przepływu pracy hostowanej przez <xref:System.ServiceModel.Activities.WorkflowServiceHost> , <xref:System.ServiceModel.Activities.Send> a <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> para może być używana w dowolnym przepływie pracy, który musi wywołać metodę w usłudze sieci Web.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-122">While the <xref:System.ServiceModel.Activities.Receive> activity can only be used in a workflow service hosted by <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> and the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair can be used in any workflow that must invoke a method on a Web service.</span></span> <span data-ttu-id="1e5b0-123">Jeśli przepływ pracy jest hostowany przy użyciu <xref:System.ServiceModel.Activities.WorkflowServiceHost> , a następnie domyślna korelacja opisana w poprzedniej sekcji ma zastosowanie, ale jeśli nie, należy jawnie skonfigurować korelację przy użyciu pożądanych <xref:System.ServiceModel.Activities.CorrelationInitializer> i <xref:System.ServiceModel.Activities.CorrelationHandle> lub za pomocą niejawnego zarządzania uchwytami <xref:System.ServiceModel.Activities.CorrelationScope> .</span><span class="sxs-lookup"><span data-stu-id="1e5b0-123">If the workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost> then the default correlation described in the previous section applies, but if not, then correlation must be configured either explicitly using the desired <xref:System.ServiceModel.Activities.CorrelationInitializer> and <xref:System.ServiceModel.Activities.CorrelationHandle>, or by using the implicit handle management of the <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span>  
  
 <span data-ttu-id="1e5b0-124">W przypadku korzystania z **Dodaj odwołanie do usługi** w usłudze z operacjami dwukierunkowymi generowane są działania, które umożliwiają wewnętrznie Zawijanie <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> aktywności pary przy użyciu jawnie określonego korelacji żądania/odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="1e5b0-124">When using **Add Service Reference** on a service with two-way operations, activities are generated that wrap a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair activity internally with the Request/Reply correlation explicitly specified.</span></span>
