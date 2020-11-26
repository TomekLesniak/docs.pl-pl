---
title: Usługi i transakcje
ms.date: 03/30/2017
helpviewer_keywords:
- service contracts [WCF], designing services and transactions
ms.assetid: 864813ff-2709-4376-912d-f5c8d318c460
ms.openlocfilehash: e60f84aafe6c62a657cd3f27c9ccdb6b65186c35
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235912"
---
# <a name="services-and-transactions"></a><span data-ttu-id="ae026-102">Usługi i transakcje</span><span class="sxs-lookup"><span data-stu-id="ae026-102">Services and Transactions</span></span>

<span data-ttu-id="ae026-103">Aplikacje Windows Communication Foundation (WCF) mogą inicjować transakcję z poziomu klienta i koordynować transakcję w ramach operacji usługi.</span><span class="sxs-lookup"><span data-stu-id="ae026-103">Windows Communication Foundation (WCF) applications can initiate a transaction from within a client and coordinate the transaction within the service operation.</span></span> <span data-ttu-id="ae026-104">Klienci mogą inicjować transakcję i wywoływać kilka operacji usługi i zapewnić, że operacje usługi są zatwierdzane lub wycofywane jako pojedyncza jednostka.</span><span class="sxs-lookup"><span data-stu-id="ae026-104">Clients can initiate a transaction and invoke several service operations and ensure that the service operations are either committed or rolled back as a single unit.</span></span>  
  
 <span data-ttu-id="ae026-105">Zachowanie transakcji można włączyć w kontrakcie usługi przez określenie <xref:System.ServiceModel.ServiceBehaviorAttribute> i ustawienie jego <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> właściwości i dla operacji usługi, które wymagają transakcji klienta.</span><span class="sxs-lookup"><span data-stu-id="ae026-105">You can enable the transaction behavior in the service contract by specifying a <xref:System.ServiceModel.ServiceBehaviorAttribute> and setting its <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> and <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> properties for service operations that require client transactions.</span></span> <span data-ttu-id="ae026-106"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>Parametr określa, czy transakcja, w której wykonywana jest metoda, jest wypełniana automatycznie, jeśli nie zostaną zgłoszone żadne Nieobsłużone wyjątki.</span><span class="sxs-lookup"><span data-stu-id="ae026-106">The <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> parameter specifies whether the transaction in which the method executes is automatically completed if no unhandled exceptions are thrown.</span></span> <span data-ttu-id="ae026-107">Aby uzyskać więcej informacji na temat tych atrybutów, zobacz [atrybuty transakcji ServiceModel](./feature-details/servicemodel-transaction-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="ae026-107">For more information about these attributes, see [ServiceModel Transaction Attributes](./feature-details/servicemodel-transaction-attributes.md).</span></span>  
  
 <span data-ttu-id="ae026-108">Prace wykonywane w ramach operacji usługi i zarządzane przez Menedżera zasobów, takie jak rejestrowanie aktualizacji bazy danych, są częścią transakcji klienta.</span><span class="sxs-lookup"><span data-stu-id="ae026-108">The work that is performed in the service operations and managed by a resource manager, such as logging database updates, is part of the client’s transaction.</span></span>  
  
 <span data-ttu-id="ae026-109">Poniższy przykład demonstruje użycie <xref:System.ServiceModel.ServiceBehaviorAttribute> atrybutów i, <xref:System.ServiceModel.OperationBehaviorAttribute> Aby kontrolować zachowanie transakcji po stronie usług.</span><span class="sxs-lookup"><span data-stu-id="ae026-109">The following sample demonstrates usage of the <xref:System.ServiceModel.ServiceBehaviorAttribute> and <xref:System.ServiceModel.OperationBehaviorAttribute> attributes to control service-side transaction behavior.</span></span>  
  
```csharp
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService: ICalculatorLog  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                           TransactionAutoComplete = true)]  
    public double Add(double n1, double n2)  
    {  
        recordToLog($"Added {n1} to {n2}");
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                               TransactionAutoComplete = true)]  
    public double Subtract(double n1, double n2)  
    {  
        recordToLog($"Subtracted {n1} from {n2}");
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                       TransactionAutoComplete = true)]  
    public double Multiply(double n1, double n2)  
    {  
        recordToLog($"Multiplied {n1} by {n2}");
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                       TransactionAutoComplete = true)]  
    public double Divide(double n1, double n2)  
    {  
        recordToLog($"Divided {n1} by {n2}", n1, n2);
        return n1 / n2;  
    }  
  
}  
```  
  
 <span data-ttu-id="ae026-110">Można włączyć transakcje i przepływ transakcji, konfigurując powiązania klienta i usługi w celu używania protokołu WS-AtomicTransaction i ustawiając [\<transactionFlow>](../configure-apps/file-schema/wcf/transactionflow.md) element na `true` , jak pokazano w poniższej konfiguracji przykładowej.</span><span class="sxs-lookup"><span data-stu-id="ae026-110">You can enable transactions and transaction flow by configuring the client and service bindings to use the WS-AtomicTransaction protocol, and setting the [\<transactionFlow>](../configure-apps/file-schema/wcf/transactionflow.md) element to `true`, as shown in the following sample configuration.</span></span>  
  
```xml  
<client>  
    <endpoint address="net.tcp://localhost/ServiceModelSamples/service"
          binding="netTcpBinding"
          bindingConfiguration="netTcpBindingWSAT"
          contract="Microsoft.ServiceModel.Samples.ICalculatorLog" />  
</client>  
  
<bindings>  
    <netTcpBinding>  
        <binding name="netTcpBindingWSAT"  
                transactionFlow="true"  
                transactionProtocol="WSAtomicTransactionOctober2004" />  
     </netTcpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="ae026-111">Klienci mogą rozpocząć transakcję, tworząc <xref:System.Transactions.TransactionScope> i wywołując operacje usługi w zakresie transakcji.</span><span class="sxs-lookup"><span data-stu-id="ae026-111">Clients can begin a transaction by creating a <xref:System.Transactions.TransactionScope> and invoking service operations within the scope of the transaction.</span></span>  
  
```csharp
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae026-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ae026-112">See also</span></span>

- [<span data-ttu-id="ae026-113">Obsługa transakcyjna w elemencie System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ae026-113">Transactional Support in System.ServiceModel</span></span>](./feature-details/transactional-support-in-system-servicemodel.md)
- [<span data-ttu-id="ae026-114">Modele transakcji</span><span class="sxs-lookup"><span data-stu-id="ae026-114">Transaction Models</span></span>](./feature-details/transaction-models.md)
- [<span data-ttu-id="ae026-115">Przepływ transakcji WS</span><span class="sxs-lookup"><span data-stu-id="ae026-115">WS Transaction Flow</span></span>](./samples/ws-transaction-flow.md)
