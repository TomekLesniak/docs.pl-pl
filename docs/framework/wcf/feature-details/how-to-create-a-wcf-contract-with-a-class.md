---
title: 'Instrukcje: Tworzenie kontraktu programu Windows Communication Foundation za pomocą klasy'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: f2164b4f4c997de764139a7a0a2aecbf91616458
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286243"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="d937f-102">Instrukcje: Tworzenie kontraktu programu Windows Communication Foundation za pomocą klasy</span><span class="sxs-lookup"><span data-stu-id="d937f-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>

<span data-ttu-id="d937f-103">Preferowanym sposobem tworzenia kontraktu Windows Communication Foundation (WCF) jest użycie interfejsu.</span><span class="sxs-lookup"><span data-stu-id="d937f-103">The preferred way of creating a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="d937f-104">Aby uzyskać więcej informacji, zobacz [How to: define a Service Contract](../how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="d937f-104">For more information, see [How to: Define a Service Contract](../how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="d937f-105">Alternatywną metodą jest utworzenie klasy, a następnie zastosowanie <xref:System.ServiceModel.ServiceContractAttribute> atrybutu do klasy bezpośrednio i <xref:System.ServiceModel.OperationContractAttribute> atrybutu do każdej metody w klasie, która jest częścią kontraktu.</span><span class="sxs-lookup"><span data-stu-id="d937f-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="d937f-106">`[ServiceContract]` i `[ServiceContractAttribute]` Wykonaj tę samą czynność.</span><span class="sxs-lookup"><span data-stu-id="d937f-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="d937f-107">Ten sam element ma wartość true dla `[OperationContract]` i `[OperationContractAttribute]` .</span><span class="sxs-lookup"><span data-stu-id="d937f-107">The same thing is true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="d937f-108">W każdym przypadku dawniej jest to skrót dla tej ostatniej.</span><span class="sxs-lookup"><span data-stu-id="d937f-108">In each case, the former is shorthand for the latter.</span></span>  
  
 <span data-ttu-id="d937f-109">Aby uzyskać więcej informacji na temat umów dotyczących usług, zobacz [Projektowanie kontraktów usług](../designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="d937f-109">For more information about service contracts, see [Designing Service Contracts](../designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="d937f-110">Tworzenie kontraktu Windows Communication Foundation z klasą</span><span class="sxs-lookup"><span data-stu-id="d937f-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1. <span data-ttu-id="d937f-111">Utwórz nową klasę przy użyciu Visual Basic, C# lub dowolnego innego języka środowiska uruchomieniowego języka wspólnego.</span><span class="sxs-lookup"><span data-stu-id="d937f-111">Create a new class using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2. <span data-ttu-id="d937f-112">Zastosuj <xref:System.ServiceModel.ServiceContractAttribute> klasę do klasy.</span><span class="sxs-lookup"><span data-stu-id="d937f-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3. <span data-ttu-id="d937f-113">Utwórz metody w klasie.</span><span class="sxs-lookup"><span data-stu-id="d937f-113">Create methods in the class.</span></span>  
  
4. <span data-ttu-id="d937f-114">Zastosuj <xref:System.ServiceModel.OperationContractAttribute> klasę do każdej metody, która musi być ujawniona w ramach publicznego kontraktu WCF.</span><span class="sxs-lookup"><span data-stu-id="d937f-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d937f-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="d937f-115">Example</span></span>  

 <span data-ttu-id="d937f-116">Poniższy przykład kodu przedstawia klasę, która definiuje kontrakt usługi.</span><span class="sxs-lookup"><span data-stu-id="d937f-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="d937f-117">Metody, do których <xref:System.ServiceModel.OperationContractAttribute> zastosowano klasę, domyślnie używają wzorca komunikatów żądanie-odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="d937f-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="d937f-118">Aby uzyskać więcej informacji na temat tego wzorca wiadomości, zobacz [How to: Create a Request-Reply Contract](how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="d937f-118">For more information about this message pattern, see [How to: Create a Request-Reply Contract](how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="d937f-119">Można również tworzyć i używać innych wzorców komunikatów przez ustawienie właściwości atrybutu.</span><span class="sxs-lookup"><span data-stu-id="d937f-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="d937f-120">Aby uzyskać więcej przykładów, zobacz [How to: Create a One-Way Contract](how-to-create-a-one-way-contract.md) i [How to: Create a Duplex kontraktu](how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="d937f-120">For more examples, see [How to: Create a One-Way Contract](how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d937f-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d937f-121">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
