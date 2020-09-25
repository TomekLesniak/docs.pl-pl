---
title: <security> dla <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 6144e5448526d7f2a7c89693f70f71a7f26c4a22
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183666"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="fd4e9-102">\<security> dla \<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="fd4e9-102">\<security> of \<basicHttpBinding></span></span>

<span data-ttu-id="fd4e9-103">Definiuje możliwości zabezpieczeń programu [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="fd4e9-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="fd4e9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fd4e9-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd4e9-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="fd4e9-105">Attributes and Elements</span></span>  

 <span data-ttu-id="fd4e9-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd4e9-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="fd4e9-107">Attributes</span></span>  
  
|<span data-ttu-id="fd4e9-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="fd4e9-108">Attribute</span></span>|<span data-ttu-id="fd4e9-109">Opis</span><span class="sxs-lookup"><span data-stu-id="fd4e9-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fd4e9-110">tryb</span><span class="sxs-lookup"><span data-stu-id="fd4e9-110">mode</span></span>|<span data-ttu-id="fd4e9-111">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-111">Optional.</span></span> <span data-ttu-id="fd4e9-112">Określa typ używanego zabezpieczenia.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-112">Specifies the type of security that is used.</span></span> <span data-ttu-id="fd4e9-113">Wartość domyślna to `None`.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-113">The default is `None`.</span></span> <span data-ttu-id="fd4e9-114">Ten atrybut jest typu <xref:System.ServiceModel.BasicHttpSecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="fd4e9-114">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="fd4e9-115">Atrybut Mode</span><span class="sxs-lookup"><span data-stu-id="fd4e9-115">mode Attribute</span></span>  
  
|<span data-ttu-id="fd4e9-116">Wartość</span><span class="sxs-lookup"><span data-stu-id="fd4e9-116">Value</span></span>|<span data-ttu-id="fd4e9-117">Opis</span><span class="sxs-lookup"><span data-stu-id="fd4e9-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fd4e9-118">Brak</span><span class="sxs-lookup"><span data-stu-id="fd4e9-118">None</span></span>|<span data-ttu-id="fd4e9-119">-Komunikaty nie są zabezpieczane podczas transferu.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-119">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="fd4e9-120">Transport</span><span class="sxs-lookup"><span data-stu-id="fd4e9-120">Transport</span></span>|<span data-ttu-id="fd4e9-121">Zabezpieczenia są udostępniane przy użyciu protokołu HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-121">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="fd4e9-122">Komunikaty protokołu SOAP są zabezpieczone przy użyciu protokołu HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-122">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="fd4e9-123">Usługa jest uwierzytelniana na kliencie przy użyciu certyfikatu X. 509 usługi.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-123">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="fd4e9-124">Klient jest uwierzytelniany przy użyciu dostarczonego obiekt ClientCredentialtype.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-124">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="fd4e9-125">Zobacz [\<transport>](transport-of-basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="fd4e9-125">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="fd4e9-126">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="fd4e9-126">Message</span></span>|<span data-ttu-id="fd4e9-127">Zabezpieczenia są udostępniane przy użyciu zabezpieczeń komunikatów protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="fd4e9-128">Domyślnie treść jest zaszyfrowana i podpisana.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="fd4e9-129">W przypadku tego powiązania system wymaga, aby certyfikat serwera został dostarczony do klienta poza pasmem.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-129">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="fd4e9-130">Jedyna prawidłowa `ClientCredentialType` dla tego powiązania to `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="fd4e9-130">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="fd4e9-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="fd4e9-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="fd4e9-132">Integralność, poufność i uwierzytelnianie serwera są udostępniane przez zabezpieczenia transportu.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-132">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="fd4e9-133">Uwierzytelnianie klienta jest zapewniane przez zabezpieczenia komunikatów protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-133">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="fd4e9-134">Ten tryb jest istotny, gdy użytkownik jest uwierzytelniany przy użyciu nazwy użytkownika/hasła i istnieje wdrożenie HTTP na potrzeby zabezpieczania transferu komunikatów.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-134">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="fd4e9-135">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="fd4e9-135">TransportCredentialOnly</span></span>|<span data-ttu-id="fd4e9-136">Ten tryb nie zapewnia integralności i poufności komunikatów.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-136">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="fd4e9-137">Zapewnia uwierzytelnianie klienta oparte na protokole HTTP.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-137">It provides http-based client authentication.</span></span> <span data-ttu-id="fd4e9-138">Ten tryb powinien być używany z zachowaniem ostrożności.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-138">This mode should be used with caution.</span></span> <span data-ttu-id="fd4e9-139">Powinna być używana w środowiskach, w których zabezpieczenia transportu są dostarczane przy użyciu innych metod (takich jak IPSec) i tylko uwierzytelnianie klienta jest udostępniane przez infrastrukturę WCF.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-139">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd4e9-140">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="fd4e9-140">Child Elements</span></span>  
  
|<span data-ttu-id="fd4e9-141">Element</span><span class="sxs-lookup"><span data-stu-id="fd4e9-141">Element</span></span>|<span data-ttu-id="fd4e9-142">Opis</span><span class="sxs-lookup"><span data-stu-id="fd4e9-142">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-basichttpbinding.md)|<span data-ttu-id="fd4e9-143">Definiuje ustawienia zabezpieczeń transportu dla podstawowej usługi HTTP.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-143">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="fd4e9-144">Ten element odnosi się do <xref:System.ServiceModel.HttpTransportSecurity> .</span><span class="sxs-lookup"><span data-stu-id="fd4e9-144">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[\<message>](message-of-basichttpbinding.md)|<span data-ttu-id="fd4e9-145">Definiuje ustawienia zabezpieczeń wiadomości dla podstawowej usługi HTTP.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-145">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="fd4e9-146">Ten element odnosi się do <xref:System.ServiceModel.BasicHttpMessageSecurity> .</span><span class="sxs-lookup"><span data-stu-id="fd4e9-146">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fd4e9-147">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="fd4e9-147">Parent Elements</span></span>  
  
|<span data-ttu-id="fd4e9-148">Element</span><span class="sxs-lookup"><span data-stu-id="fd4e9-148">Element</span></span>|<span data-ttu-id="fd4e9-149">Opis</span><span class="sxs-lookup"><span data-stu-id="fd4e9-149">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd4e9-150">powiązanie</span><span class="sxs-lookup"><span data-stu-id="fd4e9-150">binding</span></span>|<span data-ttu-id="fd4e9-151">Element Binding elementu [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="fd4e9-151">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd4e9-152">Uwagi</span><span class="sxs-lookup"><span data-stu-id="fd4e9-152">Remarks</span></span>  

 <span data-ttu-id="fd4e9-153">Domyślnie komunikat protokołu SOAP nie jest zabezpieczony i klient nie jest uwierzytelniany.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-153">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="fd4e9-154">Ten element umożliwia skonfigurowanie dodatkowych ustawień zabezpieczeń dla `basicHttpBinding` elementu.</span><span class="sxs-lookup"><span data-stu-id="fd4e9-154">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd4e9-155">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fd4e9-155">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="fd4e9-156">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="fd4e9-156">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="fd4e9-157">Wybieranie typu poświadczeń</span><span class="sxs-lookup"><span data-stu-id="fd4e9-157">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="fd4e9-158">Powiązania</span><span class="sxs-lookup"><span data-stu-id="fd4e9-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fd4e9-159">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="fd4e9-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="fd4e9-160">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="fd4e9-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
