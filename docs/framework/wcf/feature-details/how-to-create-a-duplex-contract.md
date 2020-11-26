---
title: 'Instrukcje: tworzenie kontraktu dwukierunkowego'
description: Dowiedz się, jak utworzyć umowę dupleksową, która umożliwia klientom i serwerom programu WCF wzajemne komunikowanie się ze sobą. Można inicjować wywołania do drugiego.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
ms.openlocfilehash: cce1784865a1599e69c3f604c288ef62c9c43652
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243719"
---
# <a name="how-to-create-a-duplex-contract"></a><span data-ttu-id="50a2a-104">Instrukcje: tworzenie kontraktu dwukierunkowego</span><span class="sxs-lookup"><span data-stu-id="50a2a-104">How to: Create a Duplex Contract</span></span>

<span data-ttu-id="50a2a-105">W tym temacie przedstawiono podstawowe kroki tworzenia metod, które korzystają z dwukierunkowego kontraktu.</span><span class="sxs-lookup"><span data-stu-id="50a2a-105">This topic shows the basic steps to create methods that use a duplex (two-way) contract.</span></span> <span data-ttu-id="50a2a-106">Umowa dupleksowa umożliwia klientom i serwerom komunikowanie się ze sobą niezależnie, aby można było inicjować wywołania do drugiego.</span><span class="sxs-lookup"><span data-stu-id="50a2a-106">A duplex contract allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="50a2a-107">Umowa dupleksowa to jeden z trzech wzorców komunikatów dostępnych dla usług Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="50a2a-107">The duplex contract is one of three message patterns available to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="50a2a-108">Pozostałe dwa wzorce komunikatów to jednokierunkowe i odpowiedzi na żądanie.</span><span class="sxs-lookup"><span data-stu-id="50a2a-108">The other two message patterns are one-way and request-reply.</span></span> <span data-ttu-id="50a2a-109">Umowa dupleksowa składa się z 2 1ych umów między klientem a serwerem i nie wymaga, aby wywołania metod były skorelowane.</span><span class="sxs-lookup"><span data-stu-id="50a2a-109">A duplex contract consists of two one-way contracts between the client and the server and does not require that the method calls be correlated.</span></span> <span data-ttu-id="50a2a-110">Tego rodzaju kontraktu należy używać, gdy usługa musi wysyłać zapytania do klienta, aby uzyskać więcej informacji lub jawnie podnieść zdarzenia na kliencie.</span><span class="sxs-lookup"><span data-stu-id="50a2a-110">Use this kind of contract when your service must query the client for more information or explicitly raise events on the client.</span></span> <span data-ttu-id="50a2a-111">Aby uzyskać więcej informacji na temat tworzenia aplikacji klienckiej dla kontraktu dupleksowego, zobacz [jak: dostęp do usług za pomocą kontraktu dupleksowego](how-to-access-services-with-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="50a2a-111">For more information about creating a client application for a duplex contract, see [How to: Access Services with a Duplex Contract](how-to-access-services-with-a-duplex-contract.md).</span></span> <span data-ttu-id="50a2a-112">Aby uzyskać przykład roboczy, zobacz [dwustronny](../samples/duplex.md) przykład.</span><span class="sxs-lookup"><span data-stu-id="50a2a-112">For a working sample, see the [Duplex](../samples/duplex.md) sample.</span></span>  
  
### <a name="to-create-a-duplex-contract"></a><span data-ttu-id="50a2a-113">Aby utworzyć umowę dupleksową</span><span class="sxs-lookup"><span data-stu-id="50a2a-113">To create a duplex contract</span></span>  
  
1. <span data-ttu-id="50a2a-114">Utwórz interfejs, który tworzy stronę po stronie serwera umowy dupleksowej.</span><span class="sxs-lookup"><span data-stu-id="50a2a-114">Create the interface that makes up the server side of the duplex contract.</span></span>  
  
2. <span data-ttu-id="50a2a-115">Zastosuj <xref:System.ServiceModel.ServiceContractAttribute> klasę do interfejsu.</span><span class="sxs-lookup"><span data-stu-id="50a2a-115">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3. <span data-ttu-id="50a2a-116">Zadeklaruj sygnatury metod w interfejsie.</span><span class="sxs-lookup"><span data-stu-id="50a2a-116">Declare the method signatures in the interface.</span></span>  
  
4. <span data-ttu-id="50a2a-117">Zastosuj <xref:System.ServiceModel.OperationContractAttribute> klasę do sygnatury każdej metody, która musi być częścią kontraktu publicznego.</span><span class="sxs-lookup"><span data-stu-id="50a2a-117">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
5. <span data-ttu-id="50a2a-118">Utwórz interfejs wywołania zwrotnego, który definiuje zestaw operacji, które usługa może wywoływać na kliencie.</span><span class="sxs-lookup"><span data-stu-id="50a2a-118">Create the callback interface that defines the set of operations that the service can invoke on the client.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6. <span data-ttu-id="50a2a-119">Zadeklaruj sygnatury metod w interfejsie wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="50a2a-119">Declare the method signatures in the callback interface.</span></span>  
  
7. <span data-ttu-id="50a2a-120">Zastosuj <xref:System.ServiceModel.OperationContractAttribute> klasę do sygnatury każdej metody, która musi być częścią kontraktu publicznego.</span><span class="sxs-lookup"><span data-stu-id="50a2a-120">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
8. <span data-ttu-id="50a2a-121">Połącz dwa interfejsy z umową dupleksową, ustawiając <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> Właściwość w interfejsie podstawowym na typ interfejsu wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="50a2a-121">Link the two interfaces into a duplex contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> property in the primary interface to the type of the callback interface.</span></span>  
  
### <a name="to-call-methods-on-the-client"></a><span data-ttu-id="50a2a-122">Aby wywołać metody na kliencie</span><span class="sxs-lookup"><span data-stu-id="50a2a-122">To call methods on the client</span></span>  
  
1. <span data-ttu-id="50a2a-123">W implementacji usługi głównej kontraktu Zadeklaruj zmienną dla interfejsu wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="50a2a-123">In the service's implementation of the primary contract, declare a variable for the callback interface.</span></span>  
  
2. <span data-ttu-id="50a2a-124">Ustaw zmienną na odwołanie do obiektu zwrócone przez <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> metodę <xref:System.ServiceModel.OperationContext> klasy.</span><span class="sxs-lookup"><span data-stu-id="50a2a-124">Set the variable to the object reference returned by the <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> method of the <xref:System.ServiceModel.OperationContext> class.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3. <span data-ttu-id="50a2a-125">Wywołaj metody zdefiniowane przez interfejs wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="50a2a-125">Call the methods defined by the callback interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50a2a-126">Przykład</span><span class="sxs-lookup"><span data-stu-id="50a2a-126">Example</span></span>  

 <span data-ttu-id="50a2a-127">Poniższy przykład kodu ilustruje komunikację dupleksową.</span><span class="sxs-lookup"><span data-stu-id="50a2a-127">The following code example demonstrates duplex communication.</span></span> <span data-ttu-id="50a2a-128">Kontrakt usługi zawiera operacje usługi do przeniesienia do przodu i do tyłu.</span><span class="sxs-lookup"><span data-stu-id="50a2a-128">The service’s contract contains service operations for moving forward and backward.</span></span> <span data-ttu-id="50a2a-129">Kontrakt klienta zawiera operację usługi do raportowania jej pozycji.</span><span class="sxs-lookup"><span data-stu-id="50a2a-129">The client’s contract contains a service operation for reporting its position.</span></span>  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
- <span data-ttu-id="50a2a-130">Zastosowanie <xref:System.ServiceModel.ServiceContractAttribute> atrybutów i <xref:System.ServiceModel.OperationContractAttribute> umożliwia automatyczne generowanie definicji kontraktu usługi w Web Services Description Language (WSDL).</span><span class="sxs-lookup"><span data-stu-id="50a2a-130">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes allows the automatic generation of service contract definitions in the Web Services Description Language (WSDL).</span></span>  
  
- <span data-ttu-id="50a2a-131">Użyj [Narzędzia do przesyłania metadanych modelu ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , aby pobrać dokument WSDL i (opcjonalnie) kod i konfigurację dla klienta.</span><span class="sxs-lookup"><span data-stu-id="50a2a-131">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to retrieve the WSDL document and (optional) code and configuration for a client.</span></span>  
  
- <span data-ttu-id="50a2a-132">Punkty końcowe uwidaczniające usługi dupleksowe muszą być zabezpieczone.</span><span class="sxs-lookup"><span data-stu-id="50a2a-132">Endpoints exposing duplex services must be secured.</span></span> <span data-ttu-id="50a2a-133">Gdy usługa otrzymuje komunikat o dupleksie, przegląda replikę replytą w tym komunikacie przychodzącym, aby określić, gdzie należy wysłać odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="50a2a-133">When a service receives a duplex message, it looks at the ReplyTo in that incoming message to determine where to send the reply.</span></span> <span data-ttu-id="50a2a-134">Jeśli kanał nie jest zabezpieczony, klient niezaufanego może wysłać złośliwą wiadomość z replytą maszyny docelowej, co prowadzi do odmowy usługi Maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="50a2a-134">If the channel is not secured, then an untrusted client could send a malicious message with a target machine's ReplyTo, leading to a denial of service of the target machine.</span></span> <span data-ttu-id="50a2a-135">W przypadku zwykłych komunikatów z żądaniem odpowiedzi nie jest to problem, ponieważ ReplyTo jest ignorowany, a odpowiedź jest wysyłana w kanale, w którym znajduje się pierwotny komunikat.</span><span class="sxs-lookup"><span data-stu-id="50a2a-135">With regular request-reply messages, this is not an issue, because the ReplyTo is ignored and the response is sent on the channel the original message came in on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50a2a-136">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="50a2a-136">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="50a2a-137">Instrukcje: uzyskiwanie dostępu do usług za pomocą kontraktu dwukierunkowego</span><span class="sxs-lookup"><span data-stu-id="50a2a-137">How to: Access Services with a Duplex Contract</span></span>](how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="50a2a-138">Dupleks</span><span class="sxs-lookup"><span data-stu-id="50a2a-138">Duplex</span></span>](../samples/duplex.md)
- [<span data-ttu-id="50a2a-139">Projektowanie i implementowanie usług</span><span class="sxs-lookup"><span data-stu-id="50a2a-139">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)
- [<span data-ttu-id="50a2a-140">Instrukcje: definiowanie kontraktu usługi</span><span class="sxs-lookup"><span data-stu-id="50a2a-140">How to: Define a Service Contract</span></span>](../how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="50a2a-141">Sesja</span><span class="sxs-lookup"><span data-stu-id="50a2a-141">Session</span></span>](../samples/session.md)
