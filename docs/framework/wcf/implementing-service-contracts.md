---
title: Implementowanie kontraktów usług
ms.date: 03/30/2017
helpviewer_keywords:
- implementing service contracts [WCF]
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
ms.openlocfilehash: 121922e3de62653babdac084d6bd226f7263e33c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262739"
---
# <a name="implementing-service-contracts"></a>Implementowanie kontraktów usług

Usługa jest klasą, która udostępnia klientom funkcje dostępne dla klientów w co najmniej jednym punkcie końcowym. Aby utworzyć usługę, napisz klasę implementującą kontrakt Windows Communication Foundation (WCF). Możesz to zrobić na dwa sposoby. Kontrakt można zdefiniować oddzielnie jako interfejs, a następnie utworzyć klasę, która implementuje ten interfejs. Alternatywnie można utworzyć klasę i umowę bezpośrednio przez umieszczenie <xref:System.ServiceModel.ServiceContractAttribute> atrybutu w samej klasie i <xref:System.ServiceModel.OperationContractAttribute> atrybutu w metodach dostępnych dla klientów usługi.  
  
## <a name="creating-a-service-class"></a>Tworzenie klasy usługi  

 Poniżej znajduje się przykład usługi implementującej `IMath` kontrakt, który został zdefiniowany osobno.  
  
```csharp  
// Define the IMath contract.  
[ServiceContract]  
public interface IMath  
{  
    [OperationContract]
    double Add(double A, double B);  
  
    [OperationContract]  
    double Multiply (double A, double B);  
}  
  
// Implement the IMath contract in the MathService class.  
public class MathService : IMath  
{  
    public double Add (double A, double B) { return A + B; }  
    public double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 Alternatywnie usługa może bezpośrednio uwidocznić umowę. Poniżej znajduje się przykład klasy usługi, która definiuje i implementuje `MathService` kontrakt.  
  
```csharp  
// Define the MathService contract directly on the service class.  
[ServiceContract]  
class MathService  
{  
    [OperationContract]  
    public double Add(double A, double B) { return A + B; }  
    [OperationContract]  
    private double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 Należy pamiętać, że poprzednie usługi uwidaczniają różne kontrakty, ponieważ nazwy kontraktów są różne. W pierwszym przypadku, narażony kontrakt nosi nazwę " `IMath` ", natomiast w drugim przypadku kontrakt nosi nazwę " `MathService` ".  
  
 Można ustawić kilka rzeczy na poziomach implementacji usługi i operacji, takich jak współbieżność i Tworzenie wystąpień. Aby uzyskać więcej informacji, zobacz [projektowanie i implementowanie usług](designing-and-implementing-services.md).  
  
 Po wdrożeniu kontraktu usługi należy utworzyć co najmniej jeden punkt końcowy dla usługi. Aby uzyskać więcej informacji, zobacz [Omówienie tworzenia punktów końcowych](endpoint-creation-overview.md). Aby uzyskać więcej informacji na temat sposobu uruchamiania usługi, zobacz [usługi hostingu](hosting-services.md).  
  
## <a name="see-also"></a>Zobacz też

- [Projektowanie i implementowanie usług](designing-and-implementing-services.md)
- [Instrukcje: tworzenie usługi za pomocą klasy kontraktu](./feature-details/how-to-create-a-wcf-contract-with-a-class.md)
- [Instrukcje: tworzenie usługi przy użyciu interfejsu kontraktu](./feature-details/how-to-create-a-service-with-a-contract-interface.md)
- [Określanie zachowania środowiska uruchomieniowego usługi](specifying-service-run-time-behavior.md)
