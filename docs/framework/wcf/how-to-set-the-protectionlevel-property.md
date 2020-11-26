---
title: 'Instrukcje: Ustawianie właściwości ProtectionLevel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
- ProtectionLevel property
ms.assetid: 3d4e8f80-0f9e-4a26-9899-beb6584e78df
ms.openlocfilehash: 359364228c4ab4d5b247f4f42f3ef3391f774197
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236601"
---
# <a name="how-to-set-the-protectionlevel-property"></a><span data-ttu-id="72f20-102">Instrukcje: Ustawianie właściwości ProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="72f20-102">How to: Set the ProtectionLevel Property</span></span>

<span data-ttu-id="72f20-103">Poziom ochrony można ustawić, stosując odpowiedni atrybut i ustawiając właściwość.</span><span class="sxs-lookup"><span data-stu-id="72f20-103">You can set the protection level by applying an appropriate attribute and setting the property.</span></span> <span data-ttu-id="72f20-104">Można ustawić ochronę na poziomie usługi, aby mieć wpływ na wszystkie części każdego komunikatu, lub można ustawić ochronę na coraz większych poziomach, od metod do części komunikatów.</span><span class="sxs-lookup"><span data-stu-id="72f20-104">You can set protection at the service level to affect all parts of every message, or you can set protection at increasingly granular levels, from methods to message parts.</span></span> <span data-ttu-id="72f20-105">Aby uzyskać więcej informacji na temat `ProtectionLevel` właściwości, zobacz [Opis poziomu ochrony](understanding-protection-level.md).</span><span class="sxs-lookup"><span data-stu-id="72f20-105">For more information about the `ProtectionLevel` property, see [Understanding Protection Level](understanding-protection-level.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72f20-106">Poziomy ochrony można ustawić tylko w kodzie, a nie w konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="72f20-106">You can set protection levels only in code, not in configuration.</span></span>  
  
### <a name="to-sign-all-messages-for-a-service"></a><span data-ttu-id="72f20-107">Aby podpisać wszystkie komunikaty dotyczące usługi</span><span class="sxs-lookup"><span data-stu-id="72f20-107">To sign all messages for a service</span></span>  
  
1. <span data-ttu-id="72f20-108">Utwórz interfejs dla usługi.</span><span class="sxs-lookup"><span data-stu-id="72f20-108">Create an interface for the service.</span></span>  
  
2. <span data-ttu-id="72f20-109">Zastosuj <xref:System.ServiceModel.ServiceContractAttribute> atrybut do usługi i ustaw <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> Właściwość na <xref:System.Net.Security.ProtectionLevel.Sign> , jak pokazano w poniższym kodzie (poziom domyślny to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> ).</span><span class="sxs-lookup"><span data-stu-id="72f20-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the service and set the <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.Sign>, as shown in the following code (the default level is <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>).</span></span>  
  
     [!code-csharp[C_ProtectionLevel#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#1)]
     [!code-vb[C_ProtectionLevel#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#1)]  
  
### <a name="to-sign-all-message-parts-for-an-operation"></a><span data-ttu-id="72f20-110">Aby podpisywać wszystkie części komunikatów dla operacji</span><span class="sxs-lookup"><span data-stu-id="72f20-110">To sign all message parts for an operation</span></span>  
  
1. <span data-ttu-id="72f20-111">Utwórz interfejs dla usługi i Zastosuj <xref:System.ServiceModel.ServiceContractAttribute> atrybut do interfejsu.</span><span class="sxs-lookup"><span data-stu-id="72f20-111">Create an interface for the service and apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the interface.</span></span>  
  
2. <span data-ttu-id="72f20-112">Dodaj deklarację metody do interfejsu.</span><span class="sxs-lookup"><span data-stu-id="72f20-112">Add a method declaration to the interface.</span></span>  
  
3. <span data-ttu-id="72f20-113">Zastosuj <xref:System.ServiceModel.OperationContractAttribute> atrybut do metody i ustaw <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> Właściwość na <xref:System.Net.Security.ProtectionLevel.Sign> , jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="72f20-113">Apply the <xref:System.ServiceModel.OperationContractAttribute> attribute to the method, and set the <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.Sign>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#2)]
     [!code-vb[C_ProtectionLevel#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#2)]  
  
## <a name="protecting-fault-messages"></a><span data-ttu-id="72f20-114">Ochrona komunikatów o błędach</span><span class="sxs-lookup"><span data-stu-id="72f20-114">Protecting Fault Messages</span></span>  

 <span data-ttu-id="72f20-115">Wyjątki zgłaszane w ramach usługi mogą być wysyłane do klienta jako błędy SOAP.</span><span class="sxs-lookup"><span data-stu-id="72f20-115">Exceptions that are thrown on a service can be sent to a client as SOAP faults.</span></span> <span data-ttu-id="72f20-116">Aby uzyskać więcej informacji na temat tworzenia jednoznacznie wpisanych błędów, zobacz [określanie i obsługa błędów w kontraktach i usługach](specifying-and-handling-faults-in-contracts-and-services.md) oraz [instrukcje: deklarowanie błędów w kontraktach usługi](how-to-declare-faults-in-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="72f20-116">For more information about creating strongly typed faults, see [Specifying and Handling Faults in Contracts and Services](specifying-and-handling-faults-in-contracts-and-services.md) and [How to: Declare Faults in Service Contracts](how-to-declare-faults-in-service-contracts.md).</span></span>  
  
#### <a name="to-protect-a-fault-message"></a><span data-ttu-id="72f20-117">Aby chronić komunikat o błędzie</span><span class="sxs-lookup"><span data-stu-id="72f20-117">To protect a fault message</span></span>  
  
1. <span data-ttu-id="72f20-118">Utwórz typ, który reprezentuje komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="72f20-118">Create a type that represents the fault message.</span></span> <span data-ttu-id="72f20-119">Poniższy przykład tworzy klasę o nazwie `MathFault` z dwoma polami.</span><span class="sxs-lookup"><span data-stu-id="72f20-119">The following example creates a class named `MathFault` with two fields.</span></span>  
  
2. <span data-ttu-id="72f20-120">Zastosuj <xref:System.Runtime.Serialization.DataContractAttribute> atrybut do typu i <xref:System.Runtime.Serialization.DataMemberAttribute> atrybutu do każdego pola, które powinny być serializowane, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="72f20-120">Apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the type and a <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each field that should be serialized, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#3)]
     [!code-vb[C_ProtectionLevel#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#3)]  
  
3. <span data-ttu-id="72f20-121">W interfejsie, który zwróci błąd, Zastosuj <xref:System.ServiceModel.FaultContractAttribute> atrybut do metody, która zwróci błąd, i ustaw `detailType` parametr na typ klasy Fault.</span><span class="sxs-lookup"><span data-stu-id="72f20-121">In the interface that will return the fault, apply the <xref:System.ServiceModel.FaultContractAttribute> attribute to the method that will return the fault and set the `detailType` parameter to the type of the fault class.</span></span>  
  
4. <span data-ttu-id="72f20-122">Ponadto w konstruktorze Ustaw <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A> Właściwość na <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> , jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="72f20-122">Also in the constructor, set the <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#4)]
     [!code-vb[C_ProtectionLevel#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#4)]  
  
## <a name="protecting-message-parts"></a><span data-ttu-id="72f20-123">Ochrona części komunikatów</span><span class="sxs-lookup"><span data-stu-id="72f20-123">Protecting Message Parts</span></span>  

 <span data-ttu-id="72f20-124">Użyj kontraktu komunikatu, aby chronić części wiadomości.</span><span class="sxs-lookup"><span data-stu-id="72f20-124">Use a message contract to protect parts of a message.</span></span> <span data-ttu-id="72f20-125">Aby uzyskać więcej informacji na temat umów dotyczących komunikatów, zobacz [Używanie kontraktów komunikatów](./feature-details/using-message-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="72f20-125">For more information about message contracts, see [Using Message Contracts](./feature-details/using-message-contracts.md).</span></span>  
  
#### <a name="to-protect-a-message-body"></a><span data-ttu-id="72f20-126">Aby chronić treść wiadomości</span><span class="sxs-lookup"><span data-stu-id="72f20-126">To protect a message body</span></span>  
  
1. <span data-ttu-id="72f20-127">Utwórz typ, który reprezentuje komunikat.</span><span class="sxs-lookup"><span data-stu-id="72f20-127">Create a type that represents the message.</span></span> <span data-ttu-id="72f20-128">Poniższy przykład tworzy `Company` klasę z dwoma polami `CompanyName` i `CompanyID` .</span><span class="sxs-lookup"><span data-stu-id="72f20-128">The following example creates a `Company` class with two fields, `CompanyName` and `CompanyID`.</span></span>  
  
2. <span data-ttu-id="72f20-129">Zastosuj <xref:System.ServiceModel.MessageContractAttribute> atrybut do klasy i ustaw <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A> Właściwość na <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> .</span><span class="sxs-lookup"><span data-stu-id="72f20-129">Apply the <xref:System.ServiceModel.MessageContractAttribute> attribute to the class and set the <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
3. <span data-ttu-id="72f20-130">Zastosuj <xref:System.ServiceModel.MessageHeaderAttribute> atrybut do pola, które będzie wyrażone jako nagłówek komunikatu, i ustaw `ProtectionLevel` Właściwość na <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> .</span><span class="sxs-lookup"><span data-stu-id="72f20-130">Apply the <xref:System.ServiceModel.MessageHeaderAttribute> attribute to a field that will be expressed as a message header and set the `ProtectionLevel` property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
4. <span data-ttu-id="72f20-131">Zastosuj <xref:System.ServiceModel.MessageBodyMemberAttribute> do każdego pola, które będzie wyrażone jako część treści komunikatu, i ustaw `ProtectionLevel` Właściwość na <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> , jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="72f20-131">Apply the <xref:System.ServiceModel.MessageBodyMemberAttribute> to any field that will be expressed as part of the message body, and set the `ProtectionLevel` property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, as shown in the following example.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#5)]
     [!code-vb[C_ProtectionLevel#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="72f20-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="72f20-132">Example</span></span>  

 <span data-ttu-id="72f20-133">Poniższy przykład ustawia `ProtectionLevel` Właściwość kilku klas atrybutów w różnych miejscach w usłudze.</span><span class="sxs-lookup"><span data-stu-id="72f20-133">The following example sets the `ProtectionLevel` property of several attribute classes at various places in a service.</span></span>  
  
 [!code-csharp[C_ProtectionLevel#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#6)]
 [!code-vb[C_ProtectionLevel#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="72f20-134">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="72f20-134">Compiling the Code</span></span>  

 <span data-ttu-id="72f20-135">Poniższy kod przedstawia przestrzenie nazw wymagane do skompilowania przykładowego kodu.</span><span class="sxs-lookup"><span data-stu-id="72f20-135">The following code shows the namespaces required to compile the example code.</span></span>  
  
 [!code-csharp[C_ProtectionLevel#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#0)]
 [!code-vb[C_ProtectionLevel#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="72f20-136">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="72f20-136">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.ServiceModel.MessageContractAttribute>
- <xref:System.ServiceModel.MessageBodyMemberAttribute>
- [<span data-ttu-id="72f20-137">Omówienie poziomów ochrony</span><span class="sxs-lookup"><span data-stu-id="72f20-137">Understanding Protection Level</span></span>](understanding-protection-level.md)
