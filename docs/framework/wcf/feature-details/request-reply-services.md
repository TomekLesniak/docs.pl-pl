---
title: Usługi „żądanie-odpowiedź”
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], request-reply services
- contracts [WCF], request-reply services
- WCF [WCF], request-reply services
- request-reply contracts [WCF]
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
ms.openlocfilehash: 10b82e859369dae4f57e0e13782e2375a304ab02
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295525"
---
# <a name="request-reply-services"></a>Usługi „żądanie-odpowiedź”

Usługi żądanie-odpowiedź są domyślnym typem kontraktu operacji w Windows Communication Foundation (WCF). Klienci podejmują wywołania do operacji usługi i oczekują na odpowiedź z usługi. Można wykonywać wywołania operacji usługi synchronicznie, gdzie klient jest blokowany do momentu odebrania odpowiedzi z usługi lub czasu wywołania, lub asynchronicznie, gdzie klient wykonuje wywołanie do operacji usługi, kontynuuje pracę i odbiera odpowiedź z usługi w innym wątku.  
  
 Aby utworzyć kontrakt usługi żądanie-odpowiedź, zdefiniuj kontrakt usługi i Zastosuj <xref:System.ServiceModel.OperationContractAttribute> klasę do każdej operacji, jak pokazano w poniższym przykładowym kodzie.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
```  
  
 Nie trzeba ustawiać  <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> właściwości na, `false` ponieważ jest to zachowanie domyślne.  
  
## <a name="see-also"></a>Zobacz też

- [Usługi jednokierunkowe](one-way-services.md)
- [Usługi dwukierunkowe](duplex-services.md)
