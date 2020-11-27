---
title: Rozszerzanie architektury WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
ms.openlocfilehash: b82dd4fb6a5b41a0160df8680fb1ba65d9a5bd33
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254600"
---
# <a name="extending-wcf"></a><span data-ttu-id="51472-102">Rozszerzanie architektury WCF</span><span class="sxs-lookup"><span data-stu-id="51472-102">Extending WCF</span></span>

<span data-ttu-id="51472-103">Windows Communication Foundation (WCF) pozwala modyfikować i zwiększać składniki czasu wykonywania w celu precyzyjnego kontrolowania i rozbudowania aplikacji opartych na usługach.</span><span class="sxs-lookup"><span data-stu-id="51472-103">Windows Communication Foundation (WCF) allows you to modify and extend run time components to precisely control and extend service-based applications.</span></span> <span data-ttu-id="51472-104">W tematach w tej sekcji opisano architekturę rozszerzalności.</span><span class="sxs-lookup"><span data-stu-id="51472-104">The topics in this section go in depth about the extensibility architecture.</span></span> <span data-ttu-id="51472-105">Aby uzyskać więcej informacji na temat programowania podstawowego, zobacz [podstawowe programowanie WCF](../basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="51472-105">For more information about basic programming, see [Basic WCF Programming](../basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51472-106">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="51472-106">In This Section</span></span>  

 [<span data-ttu-id="51472-107">Rozszerzanie elementu ServiceHost i warstwy modelu usług</span><span class="sxs-lookup"><span data-stu-id="51472-107">Extending ServiceHost and the Service Model Layer</span></span>](extending-servicehost-and-the-service-model-layer.md)  
 <span data-ttu-id="51472-108">Warstwa modelu usług jest odpowiedzialna za ściąganie komunikatów przychodzących z kanałów, tłumaczenie ich na wywołania metod w kodzie aplikacji i wysyłanie wyników z powrotem do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="51472-108">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span>  <span data-ttu-id="51472-109">Rozszerzenia modelu usług modyfikują lub implementują działania związane z wykonywaniem lub komunikacją, a także funkcje, w tym funkcje dyspozytora, niestandardowe zachowania, komunikat i przechwycenie parametru oraz inne funkcje rozszerzalności.</span><span class="sxs-lookup"><span data-stu-id="51472-109">Service model extensions modify or implement execution or communication behavior and features involving dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
 [<span data-ttu-id="51472-110">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="51472-110">Extending Bindings</span></span>](extending-bindings.md)  
 <span data-ttu-id="51472-111">Powiązania są obiektami, które opisują szczegóły komunikacji wymagane do nawiązania połączenia z punktem końcowym.</span><span class="sxs-lookup"><span data-stu-id="51472-111">Bindings are objects that describe the communication details required to connect to an endpoint.</span></span> <span data-ttu-id="51472-112">Rozszerzenia powiązań lub powiązania niestandardowe implementują funkcję komunikacji niestandardowej, która jest wymagana do obsługi funkcji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="51472-112">Binding extensions or custom bindings implement custom communication functionality required to support application features.</span></span>  
  
 [<span data-ttu-id="51472-113">Rozszerzanie warstwy kanału</span><span class="sxs-lookup"><span data-stu-id="51472-113">Extending the Channel Layer</span></span>](extending-the-channel-layer.md)  
 <span data-ttu-id="51472-114">Warstwa kanału znajduje się poniżej warstwy modelu usług i jest odpowiedzialna za wymianę komunikatów między klientami i usługami.</span><span class="sxs-lookup"><span data-stu-id="51472-114">The channel layer sits beneath the service model layer and is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="51472-115">Rozszerzenia kanału mogą implementować nowe funkcje protokołu, takie jak zabezpieczenia.</span><span class="sxs-lookup"><span data-stu-id="51472-115">Channel extensions can implement new protocol functionality, such as security.</span></span> <span data-ttu-id="51472-116">Rozszerzenia kanału umożliwiają również transport funkcji, takich jak implementacja nowego transportu sieciowego do przenoszenia komunikatów protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="51472-116">Channel extensions also transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
 [<span data-ttu-id="51472-117">Rozszerzanie zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="51472-117">Extending Security</span></span>](extending-security.md)  
 <span data-ttu-id="51472-118">Zabezpieczenia w programie WCF obejmują zabezpieczenia transferu (integralność, poufność i uwierzytelnianie), kontrolę dostępu (autoryzacja) i inspekcję.</span><span class="sxs-lookup"><span data-stu-id="51472-118">Security in WCF consists of transfer security (integrity, confidentiality, and authentication), access control (authorization) and auditing.</span></span> <span data-ttu-id="51472-119">Klasy Znalezione w `IdentityModel` przestrzeni nazw są używane przez funkcję WCF do kontroli dostępu.</span><span class="sxs-lookup"><span data-stu-id="51472-119">The classes found in the `IdentityModel` namespace are used by WCF for access control.</span></span> <span data-ttu-id="51472-120">Zrozumienie architektury zabezpieczeń umożliwia tworzenie niestandardowych typów zgłoszeń w celu uwzględnienia niestandardowych systemów kontroli dostępu.</span><span class="sxs-lookup"><span data-stu-id="51472-120">Understanding the security architecture allows you to create custom claim types to accommodate custom access control systems.</span></span>  
  
 [<span data-ttu-id="51472-121">Rozszerzanie systemu metadanych</span><span class="sxs-lookup"><span data-stu-id="51472-121">Extending the Metadata System</span></span>](extending-the-metadata-system.md)  
 <span data-ttu-id="51472-122">System metadanych WCF jest grupą klas i interfejsów, które reprezentują metadane wymagane do implementowania aplikacji opartych na usługach.</span><span class="sxs-lookup"><span data-stu-id="51472-122">The WCF metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="51472-123">Modyfikuj lub rozszerzaj klasy albo Implementuj i Konfiguruj interfejsy, aby wyeksportować i zaimportować niestandardowe metadane, takie jak rozszerzenia Web Services Description Language (WSDL) lub niestandardowe potwierdzenia WS-PolicyAttachments.</span><span class="sxs-lookup"><span data-stu-id="51472-123">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
 [<span data-ttu-id="51472-124">Rozszerzanie koderów i serializatorów</span><span class="sxs-lookup"><span data-stu-id="51472-124">Extending Encoders and Serializers</span></span>](extending-encoders-and-serializers.md)  
 <span data-ttu-id="51472-125">Kodery i serializatory tłumaczą dane z jednej postaci na inną.</span><span class="sxs-lookup"><span data-stu-id="51472-125">Encoders and serializers translate data from one form to another.</span></span> <span data-ttu-id="51472-126">W tematach w tej sekcji omówiono, jak zwiększyć liczbę dostarczonych klas w celu spełnienia specjalnych wymagań.</span><span class="sxs-lookup"><span data-stu-id="51472-126">The topics in this section discuss how to extend the supplied classes to meet special requirements.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="51472-127">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="51472-127">Reference</span></span>  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a><span data-ttu-id="51472-128">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="51472-128">Related Sections</span></span>  

 [<span data-ttu-id="51472-129">Podstawy programowania przy użyciu programu WCF</span><span class="sxs-lookup"><span data-stu-id="51472-129">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
 [<span data-ttu-id="51472-130">Szczegóły funkcji WCF</span><span class="sxs-lookup"><span data-stu-id="51472-130">WCF Feature Details</span></span>](../feature-details/index.md)  
  
 [<span data-ttu-id="51472-131">Wskazówki i najlepsze rozwiązania</span><span class="sxs-lookup"><span data-stu-id="51472-131">Guidelines and Best Practices</span></span>](../guidelines-and-best-practices.md)
