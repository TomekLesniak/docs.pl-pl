---
title: <security> dla <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: 48b49bf69f791f90ed5b2eea8e6d412438cd9519
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169846"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="bf74f-102">\<security> dla \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="bf74f-102">\<security> of \<ws2007HttpBinding></span></span>

<span data-ttu-id="bf74f-103">Reprezentuje ustawienia zabezpieczeń używane z [\<ws2007HttpBinding>](ws2007httpbinding.md) elementem.</span><span class="sxs-lookup"><span data-stu-id="bf74f-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="bf74f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="bf74f-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <bindings>
    <ws2007HttpBinding>
      <binding name = "String">
        <security mode="None/Message/Transport/TransportWithMessageCredential">
          <transport>
          </transport>
          <message>
          </message>
        </security>
      </binding>
    </ws2007HttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf74f-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="bf74f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="bf74f-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="bf74f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf74f-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="bf74f-107">Attributes</span></span>  
  
|<span data-ttu-id="bf74f-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="bf74f-108">Attribute</span></span>|<span data-ttu-id="bf74f-109">Opis</span><span class="sxs-lookup"><span data-stu-id="bf74f-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="bf74f-110">Obowiązkowe.</span><span class="sxs-lookup"><span data-stu-id="bf74f-110">-   Optional.</span></span> <span data-ttu-id="bf74f-111">Określa typ stosowanego zabezpieczenia.</span><span class="sxs-lookup"><span data-stu-id="bf74f-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="bf74f-112">Wartość domyślna to `Message`.</span><span class="sxs-lookup"><span data-stu-id="bf74f-112">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="bf74f-113">Ten atrybut jest typu <xref:System.ServiceModel.SecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="bf74f-113">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="bf74f-114">Atrybut Mode</span><span class="sxs-lookup"><span data-stu-id="bf74f-114">Mode Attribute</span></span>  
  
|<span data-ttu-id="bf74f-115">Wartość</span><span class="sxs-lookup"><span data-stu-id="bf74f-115">Value</span></span>|<span data-ttu-id="bf74f-116">Opis</span><span class="sxs-lookup"><span data-stu-id="bf74f-116">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="bf74f-117">Zabezpieczenia są wyłączone.</span><span class="sxs-lookup"><span data-stu-id="bf74f-117">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="bf74f-118">Zabezpieczenia są udostępniane przy użyciu protokołu HTTPS.</span><span class="sxs-lookup"><span data-stu-id="bf74f-118">Security is provided using HTTPS.</span></span> <span data-ttu-id="bf74f-119">Usługa musi być skonfigurowana z certyfikatami SSL (SSL).</span><span class="sxs-lookup"><span data-stu-id="bf74f-119">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="bf74f-120">Wiadomość jest całkowicie zabezpieczona przy użyciu protokołu HTTPS, a usługa jest uwierzytelniana przez klienta przy użyciu certyfikatu SSL usługi.</span><span class="sxs-lookup"><span data-stu-id="bf74f-120">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="bf74f-121">Uwierzytelnianie klienta jest kontrolowane przez `ClientCredentials` atrybut [\<transport>](transport-of-ws2007httpbinding.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="bf74f-121">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="bf74f-122">Zabezpieczenia są udostępniane przy użyciu zabezpieczeń komunikatów protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="bf74f-122">Security is provided using SOAP message security.</span></span> <span data-ttu-id="bf74f-123">Domyślnie treść protokołu SOAP jest zaszyfrowana i podpisana.</span><span class="sxs-lookup"><span data-stu-id="bf74f-123">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="bf74f-124">Ten tryb oferuje różne funkcje, takie jak to, czy poświadczenia usługi są dostępne na klientach poza pasmem, z którego korzysta pakiet algorytmów, oraz jaki poziom ochrony ma być stosowany do treści wiadomości za pomocą <xref:System.ServiceModel.Security.SecurityMessageProperty> .</span><span class="sxs-lookup"><span data-stu-id="bf74f-124">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="bf74f-125">Uwierzytelnianie klienta jest wykonywane raz dla każdej sesji, a wyniki uwierzytelniania są buforowane na czas trwania sesji.</span><span class="sxs-lookup"><span data-stu-id="bf74f-125">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="bf74f-126">W tym trybie protokół HTTPS zapewnia integralność, poufność i uwierzytelnianie serwera, a zabezpieczenia komunikatów protokołu SOAP zapewniają uwierzytelnianie klienta.</span><span class="sxs-lookup"><span data-stu-id="bf74f-126">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="bf74f-127">Domyślnie uwierzytelnianie klienta jest wykonywane raz dla każdej sesji, a wyniki uwierzytelniania są buforowane przez czas trwania sesji.</span><span class="sxs-lookup"><span data-stu-id="bf74f-127">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf74f-128">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="bf74f-128">Child Elements</span></span>  
  
|<span data-ttu-id="bf74f-129">Element</span><span class="sxs-lookup"><span data-stu-id="bf74f-129">Element</span></span>|<span data-ttu-id="bf74f-130">Opis</span><span class="sxs-lookup"><span data-stu-id="bf74f-130">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="bf74f-131">Definiuje ustawienia zabezpieczeń transportu.</span><span class="sxs-lookup"><span data-stu-id="bf74f-131">Defines the transport security settings.</span></span> <span data-ttu-id="bf74f-132">Ten element odnosi się do <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> typu.</span><span class="sxs-lookup"><span data-stu-id="bf74f-132">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="bf74f-133">Te ustawienia są stosowane tylko wtedy, gdy tryb jest ustawiony na transport.</span><span class="sxs-lookup"><span data-stu-id="bf74f-133">These settings are applied only when the mode is set to Transport.</span></span>|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="bf74f-134">Definiuje ustawienia zabezpieczeń wiadomości.</span><span class="sxs-lookup"><span data-stu-id="bf74f-134">Defines the security settings for the message.</span></span> <span data-ttu-id="bf74f-135">Ten element odnosi się do <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> typu.</span><span class="sxs-lookup"><span data-stu-id="bf74f-135">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="bf74f-136">Te ustawienia nie są stosowane, gdy tryb jest ustawiony na transport.</span><span class="sxs-lookup"><span data-stu-id="bf74f-136">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bf74f-137">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="bf74f-137">Parent Elements</span></span>  
  
|<span data-ttu-id="bf74f-138">Element</span><span class="sxs-lookup"><span data-stu-id="bf74f-138">Element</span></span>|<span data-ttu-id="bf74f-139">Opis</span><span class="sxs-lookup"><span data-stu-id="bf74f-139">Description</span></span>|  
|-------------|-----------------|  
|[\<ws2007HttpBinding>](ws2007httpbinding.md)|<span data-ttu-id="bf74f-140">Bezpieczne powiązanie dla aplikacji transportu HTTP.</span><span class="sxs-lookup"><span data-stu-id="bf74f-140">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf74f-141">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bf74f-141">Remarks</span></span>  

 <span data-ttu-id="bf74f-142">Ten element jest przeznaczony do współdziałania z usługami, które implementują specyfikacje WS-\*.</span><span class="sxs-lookup"><span data-stu-id="bf74f-142">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="bf74f-143">Zabezpieczenia transportu dla tego powiązania są SSL (SSL) za pośrednictwem protokołu HTTP lub HTTPS.</span><span class="sxs-lookup"><span data-stu-id="bf74f-143">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf74f-144">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bf74f-144">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="bf74f-145">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="bf74f-145">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="bf74f-146">Powiązania</span><span class="sxs-lookup"><span data-stu-id="bf74f-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="bf74f-147">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="bf74f-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="bf74f-148">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="bf74f-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
