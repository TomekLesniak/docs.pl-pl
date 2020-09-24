---
title: <transport> dla <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 8f752373c51992c51b747f5f4dc4a63910a387c6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162195"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="9cf1d-102">\<transport> dla \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="9cf1d-102">\<transport> of \<netTcpBinding></span></span>

<span data-ttu-id="9cf1d-103">Definiuje typ wymagań dotyczących zabezpieczeń na poziomie komunikatów dla punktu końcowego skonfigurowanego przy użyciu [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="9cf1d-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="9cf1d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9cf1d-104">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential">
      <transport clientCredentialType="None|Windows|Certificate"
                 protectionLevel="None|Sign|EncryptAndSign"
                 sslProtocols="Tls|Tls11|Tls12">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cf1d-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="9cf1d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9cf1d-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cf1d-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="9cf1d-107">Attributes</span></span>  
  
|<span data-ttu-id="9cf1d-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="9cf1d-108">Attribute</span></span>|<span data-ttu-id="9cf1d-109">Opis</span><span class="sxs-lookup"><span data-stu-id="9cf1d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9cf1d-110">Powiązania ClientCredentialType</span><span class="sxs-lookup"><span data-stu-id="9cf1d-110">clientCredentialType</span></span>|<span data-ttu-id="9cf1d-111">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-111">Optional.</span></span> <span data-ttu-id="9cf1d-112">Określa typ poświadczeń, które mają być używane podczas uwierzytelniania klienta przy użyciu zabezpieczeń transportu.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-112">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="9cf1d-113">— Wartość domyślna to `Windows` .</span><span class="sxs-lookup"><span data-stu-id="9cf1d-113">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="9cf1d-114">-Ten atrybut jest typu <xref:System.ServiceModel.TcpClientCredentialType> .</span><span class="sxs-lookup"><span data-stu-id="9cf1d-114">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="9cf1d-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="9cf1d-115">protectionLevel</span></span>|<span data-ttu-id="9cf1d-116">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-116">Optional.</span></span> <span data-ttu-id="9cf1d-117">Definiuje zabezpieczenia na poziomie transportu TCP.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-117">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="9cf1d-118">Komunikaty podpisywania zmniejszają ryzyko naruszenia przez osobę trzecią komunikatu podczas jego przesyłania.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="9cf1d-119">Szyfrowanie zapewnia prywatność na poziomie danych podczas transportu.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-119">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="9cf1d-120">Wartość domyślna to `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-120">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="9cf1d-121">SslProtocols określająca</span><span class="sxs-lookup"><span data-stu-id="9cf1d-121">sslProtocols</span></span>|<span data-ttu-id="9cf1d-122">Wartość flagi wyliczenia SslProtocols określająca, która określa, które SslProtocols określająca są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-122">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="9cf1d-123">Wartość domyślna to TLS&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-123">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="9cf1d-124">Zasady PolicyEnforcement</span><span class="sxs-lookup"><span data-stu-id="9cf1d-124">policyEnforcement</span></span>|<span data-ttu-id="9cf1d-125">To Wyliczenie określa, kiedy <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> należy wymusić.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-125">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="9cf1d-126">1. nigdy — zasady nigdy nie są wymuszane (ochrona rozszerzona jest wyłączona).</span><span class="sxs-lookup"><span data-stu-id="9cf1d-126">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="9cf1d-127">2. WhenSupported — zasady są wymuszane tylko wtedy, gdy klient obsługuje ochronę rozszerzoną.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-127">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="9cf1d-128">3. zawsze — zasady są zawsze wymuszane.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-128">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="9cf1d-129">Klienci, którzy nie obsługują rozszerzonej ochrony, nie będą uwierzytelniani.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-129">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="9cf1d-130">clientCredentialtype — atrybut</span><span class="sxs-lookup"><span data-stu-id="9cf1d-130">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9cf1d-131">Wartość</span><span class="sxs-lookup"><span data-stu-id="9cf1d-131">Value</span></span>|<span data-ttu-id="9cf1d-132">Opis</span><span class="sxs-lookup"><span data-stu-id="9cf1d-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9cf1d-133">Brak</span><span class="sxs-lookup"><span data-stu-id="9cf1d-133">None</span></span>|<span data-ttu-id="9cf1d-134">Klient jest anonimowy.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-134">The client is anonymous.</span></span> <span data-ttu-id="9cf1d-135">Wymaga to certyfikatu dla usługi.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-135">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="9cf1d-136">Windows</span><span class="sxs-lookup"><span data-stu-id="9cf1d-136">Windows</span></span>|<span data-ttu-id="9cf1d-137">Określa uwierzytelnianie systemu Windows klienta przy użyciu negocjacji SP (negocjowanie protokołu Kerberos).</span><span class="sxs-lookup"><span data-stu-id="9cf1d-137">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="9cf1d-138">Certyfikat</span><span class="sxs-lookup"><span data-stu-id="9cf1d-138">Certificate</span></span>|<span data-ttu-id="9cf1d-139">Klient jest uwierzytelniany przy użyciu certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-139">The client is authenticated using a certificate.</span></span> <span data-ttu-id="9cf1d-140">Powoduje to użycie negocjacji protokołu SSL i wymaga certyfikatu dla usługi.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-140">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="9cf1d-141">protectionLevel — atrybut</span><span class="sxs-lookup"><span data-stu-id="9cf1d-141">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="9cf1d-142">Wartość</span><span class="sxs-lookup"><span data-stu-id="9cf1d-142">Value</span></span>|<span data-ttu-id="9cf1d-143">Opis</span><span class="sxs-lookup"><span data-stu-id="9cf1d-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9cf1d-144">Brak</span><span class="sxs-lookup"><span data-stu-id="9cf1d-144">None</span></span>|<span data-ttu-id="9cf1d-145">Brak ochrony.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-145">No protection.</span></span>|  
|<span data-ttu-id="9cf1d-146">Znak</span><span class="sxs-lookup"><span data-stu-id="9cf1d-146">Sign</span></span>|<span data-ttu-id="9cf1d-147">Komunikaty są podpisane.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-147">Messages are signed.</span></span>|  
|<span data-ttu-id="9cf1d-148">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="9cf1d-148">EncryptAndSign</span></span>|<span data-ttu-id="9cf1d-149">— Komunikaty są szyfrowane i podpisane.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-149">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9cf1d-150">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="9cf1d-150">Child Elements</span></span>  

 <span data-ttu-id="9cf1d-151">Brak</span><span class="sxs-lookup"><span data-stu-id="9cf1d-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9cf1d-152">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="9cf1d-152">Parent Elements</span></span>  
  
|<span data-ttu-id="9cf1d-153">Element</span><span class="sxs-lookup"><span data-stu-id="9cf1d-153">Element</span></span>|<span data-ttu-id="9cf1d-154">Opis</span><span class="sxs-lookup"><span data-stu-id="9cf1d-154">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="9cf1d-155">Określa możliwości zabezpieczeń programu [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="9cf1d-155">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cf1d-156">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9cf1d-156">Remarks</span></span>  

 <span data-ttu-id="9cf1d-157">Zabezpieczenia transportu umożliwiają integralność i poufność komunikatu protokołu SOAP oraz uwierzytelnianie wzajemne.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-157">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="9cf1d-158">Jeśli w powiązaniu wybrano ten tryb zabezpieczeń, stos kanału zostanie skonfigurowany przy użyciu bezpiecznego transportu, a komunikaty protokołu SOAP są zabezpieczone za pomocą zabezpieczeń transportu, takich jak Windows (Negotiate) lub SSL przez TCP.</span><span class="sxs-lookup"><span data-stu-id="9cf1d-158">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf1d-159">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9cf1d-159">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="9cf1d-160">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="9cf1d-160">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9cf1d-161">Powiązania</span><span class="sxs-lookup"><span data-stu-id="9cf1d-161">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9cf1d-162">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="9cf1d-162">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9cf1d-163">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="9cf1d-163">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
