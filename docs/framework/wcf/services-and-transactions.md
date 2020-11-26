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
# <a name="services-and-transactions"></a>Usługi i transakcje

Aplikacje Windows Communication Foundation (WCF) mogą inicjować transakcję z poziomu klienta i koordynować transakcję w ramach operacji usługi. Klienci mogą inicjować transakcję i wywoływać kilka operacji usługi i zapewnić, że operacje usługi są zatwierdzane lub wycofywane jako pojedyncza jednostka.  
  
 Zachowanie transakcji można włączyć w kontrakcie usługi przez określenie <xref:System.ServiceModel.ServiceBehaviorAttribute> i ustawienie jego <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> właściwości i dla operacji usługi, które wymagają transakcji klienta. <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>Parametr określa, czy transakcja, w której wykonywana jest metoda, jest wypełniana automatycznie, jeśli nie zostaną zgłoszone żadne Nieobsłużone wyjątki. Aby uzyskać więcej informacji na temat tych atrybutów, zobacz [atrybuty transakcji ServiceModel](./feature-details/servicemodel-transaction-attributes.md).  
  
 Prace wykonywane w ramach operacji usługi i zarządzane przez Menedżera zasobów, takie jak rejestrowanie aktualizacji bazy danych, są częścią transakcji klienta.  
  
 Poniższy przykład demonstruje użycie <xref:System.ServiceModel.ServiceBehaviorAttribute> atrybutów i, <xref:System.ServiceModel.OperationBehaviorAttribute> Aby kontrolować zachowanie transakcji po stronie usług.  
  
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
  
 Można włączyć transakcje i przepływ transakcji, konfigurując powiązania klienta i usługi w celu używania protokołu WS-AtomicTransaction i ustawiając [\<transactionFlow>](../configure-apps/file-schema/wcf/transactionflow.md) element na `true` , jak pokazano w poniższej konfiguracji przykładowej.  
  
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
  
 Klienci mogą rozpocząć transakcję, tworząc <xref:System.Transactions.TransactionScope> i wywołując operacje usługi w zakresie transakcji.  
  
```csharp
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a>Zobacz też

- [Obsługa transakcyjna w elemencie System.ServiceModel](./feature-details/transactional-support-in-system-servicemodel.md)
- [Modele transakcji](./feature-details/transaction-models.md)
- [Przepływ transakcji WS](./samples/ws-transaction-flow.md)
