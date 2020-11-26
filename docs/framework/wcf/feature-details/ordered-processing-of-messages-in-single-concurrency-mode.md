---
title: Uporządkowane przetwarzanie komunikatów w trybie pojedynczej współbieżności
ms.date: 03/30/2017
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
ms.openlocfilehash: d70087a6dc1501f9a7f7ed057eae3dad181761ae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248022"
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a><span data-ttu-id="e6f2b-102">Uporządkowane przetwarzanie komunikatów w trybie pojedynczej współbieżności</span><span class="sxs-lookup"><span data-stu-id="e6f2b-102">Ordered Processing of Messages in Single Concurrency Mode</span></span>

<span data-ttu-id="e6f2b-103">Funkcja WCF nie gwarantuje kolejności, w której przetwarzane są komunikaty, chyba że źródłowy kanał to sesja.</span><span class="sxs-lookup"><span data-stu-id="e6f2b-103">WCF makes no guarantees about the order in which messages are processed, unless the underlying channel is sessionful.</span></span>  <span data-ttu-id="e6f2b-104">Na przykład usługa WCF korzystająca z MsmqInputChannel, która nie jest kanałem sesji, nie przetwarza komunikatów w określonej kolejności.</span><span class="sxs-lookup"><span data-stu-id="e6f2b-104">For instance, a WCF service that uses MsmqInputChannel, which is not a sessionful channel, will fail to process messages in order.</span></span> <span data-ttu-id="e6f2b-105">Istnieją pewne sytuacje, w których deweloper może chcieć wykonać przetwarzanie w kolejności, ale nie chce używać sesji.</span><span class="sxs-lookup"><span data-stu-id="e6f2b-105">There are some circumstances where a developer may want the in order processing behavior but not want to use sessions.</span></span> <span data-ttu-id="e6f2b-106">W tym temacie opisano sposób konfigurowania tego zachowania, gdy usługa jest uruchomiona w trybie pojedynczego współbieżności.</span><span class="sxs-lookup"><span data-stu-id="e6f2b-106">This topic describes how to configure this behavior when a service is running in Single Concurrency Mode.</span></span>  
  
## <a name="in-order-message-processing"></a><span data-ttu-id="e6f2b-107">Przetwarzanie komunikatów w porządku</span><span class="sxs-lookup"><span data-stu-id="e6f2b-107">In-order Message Processing</span></span>  

 <span data-ttu-id="e6f2b-108">Dodano nowy atrybut o nazwie <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> <xref:System.ServiceModel.ServiceBehaviorAttribute> .</span><span class="sxs-lookup"><span data-stu-id="e6f2b-108">A new attribute called <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> has been added to the <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span></span> <span data-ttu-id="e6f2b-109">Gdy <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> jest ustawiona na wartość true i <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> jest ustawiona na <xref:System.ServiceModel.ConcurrencyMode.Single> Komunikaty wysyłane do usługi, zostanie przetworzona w kolejności.</span><span class="sxs-lookup"><span data-stu-id="e6f2b-109">When <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> is set to true and <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to <xref:System.ServiceModel.ConcurrencyMode.Single> messages sent to the service will be processed in order.</span></span> <span data-ttu-id="e6f2b-110">Poniższy fragment kodu ilustruje sposób ustawiania tych atrybutów.</span><span class="sxs-lookup"><span data-stu-id="e6f2b-110">The following code snippet illustrates how to set these attributes.</span></span>  
  
```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 <span data-ttu-id="e6f2b-111">Jeśli <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> jest ustawiona na inną wartość, <xref:System.InvalidOperationException> zostanie zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="e6f2b-111">If <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to any other value, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f2b-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e6f2b-112">See also</span></span>

- [<span data-ttu-id="e6f2b-113">Sesje, tworzenie wystąpień i współbieżność</span><span class="sxs-lookup"><span data-stu-id="e6f2b-113">Sessions, Instancing, and Concurrency</span></span>](sessions-instancing-and-concurrency.md)
- [<span data-ttu-id="e6f2b-114">Współbieżność</span><span class="sxs-lookup"><span data-stu-id="e6f2b-114">Concurrency</span></span>](../samples/concurrency.md)
