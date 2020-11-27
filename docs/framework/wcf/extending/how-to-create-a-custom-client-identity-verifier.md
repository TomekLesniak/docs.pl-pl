---
title: 'Instrukcje: tworzenie niestandardowego weryfikatora tożsamości klienta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f2d34e43-fa8b-46d2-91cf-d2960e13e16b
ms.openlocfilehash: 84982aca06bacb5718855602872fe4dab2376a9d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256069"
---
# <a name="how-to-create-a-custom-client-identity-verifier"></a><span data-ttu-id="e7959-102">Instrukcje: tworzenie niestandardowego weryfikatora tożsamości klienta</span><span class="sxs-lookup"><span data-stu-id="e7959-102">How to: Create a Custom Client Identity Verifier</span></span>

<span data-ttu-id="e7959-103">Funkcja *Identity* programu Windows Communication Foundation (WCF) pozwala klientowi określić z wyprzedzeniem oczekiwaną tożsamość usługi.</span><span class="sxs-lookup"><span data-stu-id="e7959-103">The *identity* feature of Windows Communication Foundation (WCF) enables a client to specify in advance the expected identity of the service.</span></span> <span data-ttu-id="e7959-104">Za każdym razem, gdy serwer uwierzytelnia się na kliencie, tożsamość jest sprawdzana pod kątem oczekiwanej tożsamości.</span><span class="sxs-lookup"><span data-stu-id="e7959-104">Whenever a server authenticates itself to the client, the identity is checked against the expected identity.</span></span> <span data-ttu-id="e7959-105">(Aby uzyskać wyjaśnienie tożsamości i sposobu jej działania, zobacz [tożsamość usługi i uwierzytelnianie](../feature-details/service-identity-and-authentication.md)).</span><span class="sxs-lookup"><span data-stu-id="e7959-105">(For an explanation of identity and how it works, see [Service Identity and Authentication](../feature-details/service-identity-and-authentication.md).)</span></span>  
  
 <span data-ttu-id="e7959-106">W razie konieczności weryfikacja można dostosować przy użyciu niestandardowego weryfikatora tożsamości.</span><span class="sxs-lookup"><span data-stu-id="e7959-106">If needed, the verification can be customized using a custom identity verifier.</span></span> <span data-ttu-id="e7959-107">Można na przykład przeprowadzić dodatkowe testy weryfikacyjne tożsamości usługi.</span><span class="sxs-lookup"><span data-stu-id="e7959-107">For example, you can perform additional service identity verification checks.</span></span> <span data-ttu-id="e7959-108">W tym przykładzie weryfikator tożsamości niestandardowej sprawdza dodatkowe oświadczenia w certyfikacie X. 509 zwróconym z serwera.</span><span class="sxs-lookup"><span data-stu-id="e7959-108">In this example, the custom identity verifier checks additional claims in the X.509 certificate returned from the server.</span></span> <span data-ttu-id="e7959-109">Aby zapoznać się z przykładową aplikacją, zobacz [przykład Identity Service](../samples/service-identity-sample.md).</span><span class="sxs-lookup"><span data-stu-id="e7959-109">For a sample application, see [Service Identity Sample](../samples/service-identity-sample.md).</span></span>  
  
### <a name="to-extend-the-endpointidentity-class"></a><span data-ttu-id="e7959-110">Aby zwiększyć klasę EndpointIdentity</span><span class="sxs-lookup"><span data-stu-id="e7959-110">To extend the EndpointIdentity class</span></span>  
  
1. <span data-ttu-id="e7959-111">Zdefiniuj nową klasę, która dziedziczy z <xref:System.ServiceModel.EndpointIdentity> klasy.</span><span class="sxs-lookup"><span data-stu-id="e7959-111">Define a new class that derives from the <xref:System.ServiceModel.EndpointIdentity> class.</span></span> <span data-ttu-id="e7959-112">Ten przykład nazywa rozszerzenie `OrgEndpointIdentity` .</span><span class="sxs-lookup"><span data-stu-id="e7959-112">This example names the extension `OrgEndpointIdentity`.</span></span>  
  
2. <span data-ttu-id="e7959-113">Dodaj prywatne elementy członkowskie wraz z właściwościami, które będą używane przez <xref:System.ServiceModel.Security.IdentityVerifier> klasę rozszerzoną do przeprowadzenia sprawdzania tożsamości dla oświadczeń w tokenie zabezpieczającym zwracanym przez usługę.</span><span class="sxs-lookup"><span data-stu-id="e7959-113">Add private members along with properties that will be used by the extended <xref:System.ServiceModel.Security.IdentityVerifier> class to perform the identity check against claims in the security token returned from the service.</span></span> <span data-ttu-id="e7959-114">Ten przykład definiuje jedną właściwość: `OrganizationClaim` Właściwość.</span><span class="sxs-lookup"><span data-stu-id="e7959-114">This example defines one property: the `OrganizationClaim` property.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
     [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
### <a name="to-extend-the-identityverifier-class"></a><span data-ttu-id="e7959-115">Aby zwiększyć klasę IdentityVerifier</span><span class="sxs-lookup"><span data-stu-id="e7959-115">To extend the IdentityVerifier class</span></span>  
  
1. <span data-ttu-id="e7959-116">Zdefiniuj nową klasę, która pochodzi od <xref:System.ServiceModel.Security.IdentityVerifier> .</span><span class="sxs-lookup"><span data-stu-id="e7959-116">Define a new class that derives from <xref:System.ServiceModel.Security.IdentityVerifier>.</span></span> <span data-ttu-id="e7959-117">Ten przykład nazywa rozszerzenie `CustomIdentityVerifier` .</span><span class="sxs-lookup"><span data-stu-id="e7959-117">This example names the extension `CustomIdentityVerifier`.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#7)]
     [!code-vb[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#7)]  
  
2. <span data-ttu-id="e7959-118">Zastąp <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A> metodę.</span><span class="sxs-lookup"><span data-stu-id="e7959-118">Override the <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A> method.</span></span> <span data-ttu-id="e7959-119">Metoda określa, czy sprawdzanie tożsamości zakończyło się powodzeniem, czy niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="e7959-119">The method determines whether the identity check succeeded or failed.</span></span>  
  
3. <span data-ttu-id="e7959-120">`CheckAccess`Metoda ma dwa parametry.</span><span class="sxs-lookup"><span data-stu-id="e7959-120">The `CheckAccess` method has two parameters.</span></span> <span data-ttu-id="e7959-121">Pierwszy jest wystąpieniem <xref:System.ServiceModel.EndpointIdentity> klasy.</span><span class="sxs-lookup"><span data-stu-id="e7959-121">The first is an instance of the <xref:System.ServiceModel.EndpointIdentity> class.</span></span> <span data-ttu-id="e7959-122">Drugim jest wystąpieniem <xref:System.IdentityModel.Policy.AuthorizationContext> klasy.</span><span class="sxs-lookup"><span data-stu-id="e7959-122">The second is an instance of the <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span>  
  
     <span data-ttu-id="e7959-123">W implementacji metody Sprawdź kolekcję oświadczeń zwracanych przez <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> Właściwość <xref:System.IdentityModel.Policy.AuthorizationContext> klasy i wykonaj testy uwierzytelniania zgodnie z wymaganiami.</span><span class="sxs-lookup"><span data-stu-id="e7959-123">In the method implementation, examine the collection of claims returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> class, and perform authentication checks as required.</span></span> <span data-ttu-id="e7959-124">Ten przykład rozpoczyna się od znalezienia wszelkich roszczeń typu "nazwa wyróżniająca", a następnie porównuje nazwę z rozszerzeniem <xref:System.ServiceModel.EndpointIdentity> ( `OrgEndpointIdentity` ).</span><span class="sxs-lookup"><span data-stu-id="e7959-124">This example begins by finding any claim that is of type "Distinguished Name" and then compares the name to the extension of the <xref:System.ServiceModel.EndpointIdentity> (`OrgEndpointIdentity`).</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#1)]
     [!code-vb[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#1)]  
  
### <a name="to-implement-the-trygetidentity-method"></a><span data-ttu-id="e7959-125">Aby zaimplementować metodę TryGetIdentity</span><span class="sxs-lookup"><span data-stu-id="e7959-125">To implement the TryGetIdentity method</span></span>  
  
1. <span data-ttu-id="e7959-126">Zaimplementuj <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A> metodę, która określa, czy wystąpienie <xref:System.ServiceModel.EndpointIdentity> klasy może być zwracane przez klienta.</span><span class="sxs-lookup"><span data-stu-id="e7959-126">Implement the <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A> method, which determines whether an instance of the <xref:System.ServiceModel.EndpointIdentity> class can be returned by the client.</span></span> <span data-ttu-id="e7959-127">Infrastruktura WCF najpierw wywołuje implementację `TryGetIdentity` metody w celu pobrania tożsamości usługi z wiadomości.</span><span class="sxs-lookup"><span data-stu-id="e7959-127">The WCF infrastructure calls the implementation of the `TryGetIdentity` method first to retrieve the service's identity from the message.</span></span> <span data-ttu-id="e7959-128">Następnie infrastruktura wywołuje `CheckAccess` implementację z zwracanymi `EndpointIdentity` i <xref:System.IdentityModel.Policy.AuthorizationContext> .</span><span class="sxs-lookup"><span data-stu-id="e7959-128">Next, the infrastructure calls the `CheckAccess` implementation with the returned `EndpointIdentity` and <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span>  
  
2. <span data-ttu-id="e7959-129">W `TryGetIdentity` metodzie należy umieścić następujący kod:</span><span class="sxs-lookup"><span data-stu-id="e7959-129">In the `TryGetIdentity` method, put the following code:</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#2)]
     [!code-vb[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#2)]  
  
### <a name="to-implement-a-custom-binding-and-set-the-custom-identityverifier"></a><span data-ttu-id="e7959-130">Aby zaimplementować niestandardowe powiązanie i ustawić niestandardowe IdentityVerifier</span><span class="sxs-lookup"><span data-stu-id="e7959-130">To implement a custom binding and set the custom IdentityVerifier</span></span>  
  
1. <span data-ttu-id="e7959-131">Utwórz metodę, która zwraca <xref:System.ServiceModel.Channels.Binding> obiekt.</span><span class="sxs-lookup"><span data-stu-id="e7959-131">Create a method that returns a <xref:System.ServiceModel.Channels.Binding> object.</span></span> <span data-ttu-id="e7959-132">Ten przykład rozpoczyna Tworzenie wystąpienia <xref:System.ServiceModel.WSHttpBinding> klasy i ustawia jego tryb zabezpieczeń na <xref:System.ServiceModel.SecurityMode.Message> , a <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> do <xref:System.ServiceModel.MessageCredentialType.None> .</span><span class="sxs-lookup"><span data-stu-id="e7959-132">This example begins creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class and sets its security mode to <xref:System.ServiceModel.SecurityMode.Message>, and its <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> to <xref:System.ServiceModel.MessageCredentialType.None>.</span></span>  
  
2. <span data-ttu-id="e7959-133">Utwórz <xref:System.ServiceModel.Channels.BindingElementCollection> za pomocą <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="e7959-133">Create a <xref:System.ServiceModel.Channels.BindingElementCollection> using the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3. <span data-ttu-id="e7959-134">Zwróć <xref:System.ServiceModel.Channels.SecurityBindingElement> z kolekcji i przerzucaj ją do <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> zmiennej.</span><span class="sxs-lookup"><span data-stu-id="e7959-134">Return the <xref:System.ServiceModel.Channels.SecurityBindingElement> from the collection and cast it to a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> variable.</span></span>  
  
4. <span data-ttu-id="e7959-135">Ustaw <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> Właściwość <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> klasy na nowe wystąpienie `CustomIdentityVerifier` klasy utworzonej wcześniej.</span><span class="sxs-lookup"><span data-stu-id="e7959-135">Set the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> property of the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> class to a new instance of the `CustomIdentityVerifier` class created previously.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#3)]
     [!code-vb[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#3)]  
  
5. <span data-ttu-id="e7959-136">Zwracane niestandardowe powiązanie służy do tworzenia wystąpienia klienta i klasy.</span><span class="sxs-lookup"><span data-stu-id="e7959-136">The custom binding that is returned is used to create an instance of the client and class.</span></span> <span data-ttu-id="e7959-137">Klient może następnie wykonać sprawdzenie niestandardowej weryfikacji tożsamości usługi, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="e7959-137">The client can then perform a custom identity verification check of the service as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#4)]
     [!code-vb[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="e7959-138">Przykład</span><span class="sxs-lookup"><span data-stu-id="e7959-138">Example</span></span>  

 <span data-ttu-id="e7959-139">Poniższy przykład pokazuje kompletną implementację <xref:System.ServiceModel.Security.IdentityVerifier> klasy.</span><span class="sxs-lookup"><span data-stu-id="e7959-139">The following example shows a complete implementation of the <xref:System.ServiceModel.Security.IdentityVerifier> class.</span></span>  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#5)]
 [!code-vb[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="e7959-140">Przykład</span><span class="sxs-lookup"><span data-stu-id="e7959-140">Example</span></span>  

 <span data-ttu-id="e7959-141">Poniższy przykład pokazuje kompletną implementację <xref:System.ServiceModel.EndpointIdentity> klasy.</span><span class="sxs-lookup"><span data-stu-id="e7959-141">The following example shows a complete implementation of the <xref:System.ServiceModel.EndpointIdentity> class.</span></span>  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
 [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="e7959-142">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e7959-142">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- <xref:System.ServiceModel.EndpointIdentity>
- <xref:System.ServiceModel.Security.IdentityVerifier>
- [<span data-ttu-id="e7959-143">Tożsamość usług — przykład</span><span class="sxs-lookup"><span data-stu-id="e7959-143">Service Identity Sample</span></span>](../samples/service-identity-sample.md)
- [<span data-ttu-id="e7959-144">Zasady autoryzacji</span><span class="sxs-lookup"><span data-stu-id="e7959-144">Authorization Policy</span></span>](../samples/authorization-policy.md)
