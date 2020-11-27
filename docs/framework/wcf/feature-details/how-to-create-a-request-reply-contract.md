---
title: 'Instrukcje: tworzenie kontraktu „żądanie-odpowiedź”'
ms.date: 03/30/2017
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
ms.openlocfilehash: 506ce527348286bb53223c64245c74e4cb21879a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286555"
---
# <a name="how-to-create-a-request-reply-contract"></a><span data-ttu-id="c38a7-102">Instrukcje: tworzenie kontraktu „żądanie-odpowiedź”</span><span class="sxs-lookup"><span data-stu-id="c38a7-102">How to: Create a Request-Reply Contract</span></span>

<span data-ttu-id="c38a7-103">Kontrakt typu żądanie-odpowiedź określa metodę, która zwraca odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="c38a7-103">A request-reply contract specifies a method that returns a reply.</span></span> <span data-ttu-id="c38a7-104">Odpowiedź musi być wysłana i skorelowane do żądania zgodnie z warunkami tego kontraktu.</span><span class="sxs-lookup"><span data-stu-id="c38a7-104">The reply must be sent and correlated to the request under the terms of this contract.</span></span> <span data-ttu-id="c38a7-105">Nawet jeśli metoda nie zwróci odpowiedzi ( `void` w języku C# lub `Sub` w Visual Basic), infrastruktura tworzy i wysyła pusty komunikat do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="c38a7-105">Even if the method returns no reply (`void` in C#, or a `Sub` in Visual Basic), the infrastructure creates and sends an empty message to the caller.</span></span> <span data-ttu-id="c38a7-106">Aby zapobiec wysyłaniu pustego komunikatu odpowiedzi, użyj kontraktu jednokierunkowego dla operacji.</span><span class="sxs-lookup"><span data-stu-id="c38a7-106">To prevent the sending of an empty reply message, use a one-way contract for the operation.</span></span>  
  
### <a name="to-create-a-request-reply-contract"></a><span data-ttu-id="c38a7-107">Aby utworzyć kontrakt typu żądanie-odpowiedź</span><span class="sxs-lookup"><span data-stu-id="c38a7-107">To create a request-reply contract</span></span>  
  
1. <span data-ttu-id="c38a7-108">Utwórz interfejs w wybranym języku programowania.</span><span class="sxs-lookup"><span data-stu-id="c38a7-108">Create an interface in the programming language of your choice.</span></span>  
  
2. <span data-ttu-id="c38a7-109">Zastosuj <xref:System.ServiceModel.ServiceContractAttribute> atrybut do interfejsu.</span><span class="sxs-lookup"><span data-stu-id="c38a7-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the interface.</span></span>  
  
3. <span data-ttu-id="c38a7-110">Zastosuj <xref:System.ServiceModel.OperationContractAttribute> atrybut do poszczególnych metod, które mogą być wywoływane przez klientów.</span><span class="sxs-lookup"><span data-stu-id="c38a7-110">Apply the <xref:System.ServiceModel.OperationContractAttribute> attribute to each method that clients can invoke.</span></span>  
  
4. <span data-ttu-id="c38a7-111">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="c38a7-111">Optional.</span></span> <span data-ttu-id="c38a7-112">Ustaw wartość <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> właściwości na `true` , aby zapobiec wysyłaniu pustego komunikatu odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="c38a7-112">Set the value of the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `true` to prevent the sending of an empty reply message.</span></span> <span data-ttu-id="c38a7-113">Domyślnie wszystkie operacje są kontraktami żądanie-odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="c38a7-113">By default, all operations are request-reply contracts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c38a7-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="c38a7-114">Example</span></span>  

 <span data-ttu-id="c38a7-115">Poniższy przykład definiuje kontrakt usługi kalkulatora, która dostarcza `Add` `Subtract` metody i.</span><span class="sxs-lookup"><span data-stu-id="c38a7-115">The following sample defines a contract for a calculator service that provides `Add` and `Subtract` methods.</span></span> <span data-ttu-id="c38a7-116">`Multiply`Metoda nie jest częścią kontraktu, ponieważ nie jest oznaczona przez <xref:System.ServiceModel.OperationContractAttribute> klasę i dlatego nie jest dostępna dla klientów.</span><span class="sxs-lookup"><span data-stu-id="c38a7-116">The `Multiply` method is not part of the contract because it is not marked by the <xref:System.ServiceModel.OperationContractAttribute> class and so it is not accessible to clients.</span></span>  
  
```csharp
using System.ServiceModel;

[ServiceContract]
public interface ICalculator
{
    [OperationContract]
    // It would be equivalent to write explicitly:
    // [OperationContract(IsOneWay=false)]
    int Add(int a, int b);

    [OperationContract]
    int Subtract(int a, int b);

    int Multiply(int a, int b)
}
```
  
- <span data-ttu-id="c38a7-117">Aby uzyskać więcej informacji na temat określania kontraktów operacji, zobacz <xref:System.ServiceModel.OperationContractAttribute> Klasa i <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> Właściwość.</span><span class="sxs-lookup"><span data-stu-id="c38a7-117">For more information about how to specify operation contracts, see the <xref:System.ServiceModel.OperationContractAttribute> class and the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property.</span></span>  
  
- <span data-ttu-id="c38a7-118">Zastosowanie <xref:System.ServiceModel.ServiceContractAttribute> atrybutów i <xref:System.ServiceModel.OperationContractAttribute> powoduje automatyczne generowanie definicji kontraktu usługi w dokumencie Web Services Description Language (WSDL) po wdrożeniu usługi.</span><span class="sxs-lookup"><span data-stu-id="c38a7-118">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes causes the automatic generation of service contract definitions in a Web Services Description Language (WSDL) document once the service is deployed.</span></span> <span data-ttu-id="c38a7-119">Dokument zostanie pobrany przez dołączenie `?wsdl` do podstawowego adresu http dla usługi.</span><span class="sxs-lookup"><span data-stu-id="c38a7-119">The document is downloaded by appending `?wsdl` to the HTTP base address for the service.</span></span> <span data-ttu-id="c38a7-120">Na przykład `http://microsoft/CalculatorService?wsdl`</span><span class="sxs-lookup"><span data-stu-id="c38a7-120">For example, `http://microsoft/CalculatorService?wsdl`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c38a7-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c38a7-121">See also</span></span>

- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="c38a7-122">Projektowanie kontraktów usług</span><span class="sxs-lookup"><span data-stu-id="c38a7-122">Designing Service Contracts</span></span>](../designing-service-contracts.md)
- [<span data-ttu-id="c38a7-123">Instrukcje: tworzenie kontraktu dwukierunkowego</span><span class="sxs-lookup"><span data-stu-id="c38a7-123">How to: Create a Duplex Contract</span></span>](how-to-create-a-duplex-contract.md)
