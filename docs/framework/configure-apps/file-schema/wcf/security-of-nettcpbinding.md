---
title: <security> dla <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
ms.openlocfilehash: d39e3e5e655817aa91c5301274a860a00a6ab7ef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169989"
---
# <a name="security-of-nettcpbinding"></a><span data-ttu-id="04433-102">\<security> dla \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="04433-102">\<security> of \<netTcpBinding></span></span>

<span data-ttu-id="04433-103">Definiuje ustawienia zabezpieczeń dla powiązania.</span><span class="sxs-lookup"><span data-stu-id="04433-103">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="04433-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="04433-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             protectionLevel="None/Sign/EncryptAndSign" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04433-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="04433-105">Attributes and Elements</span></span>  

 <span data-ttu-id="04433-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="04433-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04433-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="04433-107">Attributes</span></span>  
  
|<span data-ttu-id="04433-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="04433-108">Attribute</span></span>|<span data-ttu-id="04433-109">Opis</span><span class="sxs-lookup"><span data-stu-id="04433-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="04433-110">tryb</span><span class="sxs-lookup"><span data-stu-id="04433-110">mode</span></span>|<span data-ttu-id="04433-111">Opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="04433-111">Optional.</span></span> <span data-ttu-id="04433-112">Określa typ stosowanego zabezpieczenia.</span><span class="sxs-lookup"><span data-stu-id="04433-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="04433-113">Poniżej przedstawiono prawidłowe wartości.</span><span class="sxs-lookup"><span data-stu-id="04433-113">Valid values are shown below.</span></span> <span data-ttu-id="04433-114">Wartość domyślna to `Transport`.</span><span class="sxs-lookup"><span data-stu-id="04433-114">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="04433-115">Ten atrybut jest typu <xref:System.ServiceModel.SecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="04433-115">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="04433-116">Atrybut Mode</span><span class="sxs-lookup"><span data-stu-id="04433-116">mode Attribute</span></span>  
  
|<span data-ttu-id="04433-117">Wartość</span><span class="sxs-lookup"><span data-stu-id="04433-117">Value</span></span>|<span data-ttu-id="04433-118">Opis</span><span class="sxs-lookup"><span data-stu-id="04433-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="04433-119">Brak</span><span class="sxs-lookup"><span data-stu-id="04433-119">None</span></span>|<span data-ttu-id="04433-120">Zabezpieczenia są wyłączone.</span><span class="sxs-lookup"><span data-stu-id="04433-120">Security is disabled.</span></span>|  
|<span data-ttu-id="04433-121">Transport</span><span class="sxs-lookup"><span data-stu-id="04433-121">Transport</span></span>|<span data-ttu-id="04433-122">Zabezpieczenia transportu są udostępniane przy użyciu protokołu TLS przez TCP lub SPNego.</span><span class="sxs-lookup"><span data-stu-id="04433-122">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="04433-123">Może być konieczne skonfigurowanie usługi przy użyciu certyfikatów SSL.</span><span class="sxs-lookup"><span data-stu-id="04433-123">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="04433-124">Istnieje możliwość kontrolowania poziomu ochrony w tym trybie.</span><span class="sxs-lookup"><span data-stu-id="04433-124">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="04433-125">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="04433-125">Message</span></span>|<span data-ttu-id="04433-126">Zabezpieczenia są udostępniane przy użyciu zabezpieczeń komunikatów protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="04433-126">Security is provided using SOAP message security.</span></span> <span data-ttu-id="04433-127">Domyślnie treść protokołu SOAP jest zaszyfrowana i podpisana.</span><span class="sxs-lookup"><span data-stu-id="04433-127">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="04433-128">Ten tryb oferuje różne funkcje, takie jak to, czy poświadczenia usługi są dostępne na kliencie poza pasmem, pakiet algorytmów do użycia oraz jaki poziom ochrony ma być stosowany do treści wiadomości.</span><span class="sxs-lookup"><span data-stu-id="04433-128">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="04433-129">Uwierzytelnianie klienta jest wykonywane raz na sesję, a wyniki uwierzytelniania są buforowane na czas trwania sesji.</span><span class="sxs-lookup"><span data-stu-id="04433-129">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="04433-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="04433-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="04433-131">Zabezpieczenia transportu są powiązane z zabezpieczeniami komunikatów.</span><span class="sxs-lookup"><span data-stu-id="04433-131">Transport security is coupled with message security.</span></span> <span data-ttu-id="04433-132">Zabezpieczenia transportu są udostępniane przez protokół TLS przez TCP lub SPNego oraz zapewniają integralność, poufność i uwierzytelnianie serwera.</span><span class="sxs-lookup"><span data-stu-id="04433-132">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="04433-133">Zabezpieczenia komunikatów protokołu SOAP zapewniają uwierzytelnianie klienta.</span><span class="sxs-lookup"><span data-stu-id="04433-133">SOAP message security provides client authentication.</span></span> <span data-ttu-id="04433-134">Domyślnie uwierzytelnianie klienta jest wykonywane raz na sesję, a wyniki uwierzytelniania są buforowane przez czas trwania sesji.</span><span class="sxs-lookup"><span data-stu-id="04433-134">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04433-135">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="04433-135">Child Elements</span></span>  
  
|<span data-ttu-id="04433-136">Element</span><span class="sxs-lookup"><span data-stu-id="04433-136">Element</span></span>|<span data-ttu-id="04433-137">Opis</span><span class="sxs-lookup"><span data-stu-id="04433-137">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-nettcpbinding.md)|<span data-ttu-id="04433-138">Definiuje ustawienia zabezpieczeń transportu.</span><span class="sxs-lookup"><span data-stu-id="04433-138">Defines the security settings for the transport.</span></span> <span data-ttu-id="04433-139">Ten element jest typu <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement> .</span><span class="sxs-lookup"><span data-stu-id="04433-139">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[\<message>](message-element-of-nettcpbinding.md)|<span data-ttu-id="04433-140">Definiuje ustawienia zabezpieczeń wiadomości.</span><span class="sxs-lookup"><span data-stu-id="04433-140">Defines the security settings for the message.</span></span> <span data-ttu-id="04433-141">Ten element jest typu <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement> .</span><span class="sxs-lookup"><span data-stu-id="04433-141">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="04433-142">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="04433-142">Parent Elements</span></span>  
  
|<span data-ttu-id="04433-143">Element</span><span class="sxs-lookup"><span data-stu-id="04433-143">Element</span></span>|<span data-ttu-id="04433-144">Opis</span><span class="sxs-lookup"><span data-stu-id="04433-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04433-145">powiązanie</span><span class="sxs-lookup"><span data-stu-id="04433-145">binding</span></span>|<span data-ttu-id="04433-146">Element Binding elementu [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="04433-146">The binding element of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04433-147">Uwagi</span><span class="sxs-lookup"><span data-stu-id="04433-147">Remarks</span></span>  

 <span data-ttu-id="04433-148">Wszystkie powiązania standardowe zawierają parametry służące do kontrolowania wymagań dotyczących zabezpieczeń transferu.</span><span class="sxs-lookup"><span data-stu-id="04433-148">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="04433-149">Parametry te zazwyczaj obejmują tryb zabezpieczeń, który określa, czy używane są zabezpieczenia na poziomie wiadomości lub transportu oraz wybór typu poświadczeń klienta.</span><span class="sxs-lookup"><span data-stu-id="04433-149">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="04433-150">Na podstawie wyboru opcji tych parametrów istnieje stos kanału z odpowiednimi zabezpieczeniami.</span><span class="sxs-lookup"><span data-stu-id="04433-150">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="04433-151">Powiązania dostarczone przez system Windows Communication Foundation (WCF) są zestawem zaprojektowanym pod kątem spełnienia niektórych typowych wymagań scenariusza.</span><span class="sxs-lookup"><span data-stu-id="04433-151">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="04433-152">Każde z tych powiązań umożliwia określenie wymagań dotyczących zabezpieczeń dla niektórych konkretnych scenariuszy.</span><span class="sxs-lookup"><span data-stu-id="04433-152">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="04433-153">Ten element konfiguracji zawiera specyfikacje zabezpieczeń dla programu `netTcpBinding` .</span><span class="sxs-lookup"><span data-stu-id="04433-153">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="04433-154">Jest to bezpieczne, niezawodne i zoptymalizowane powiązanie odpowiednie dla komunikacji między komputerami.</span><span class="sxs-lookup"><span data-stu-id="04433-154">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="04433-155">Domyślnie generuje stos komunikacji środowiska uruchomieniowego obsługujący protokół TCP na potrzeby dostarczania komunikatów i zabezpieczenia systemu Windows w celu zapewnienia bezpieczeństwa i uwierzytelniania komunikatów oraz szyfrowania wiadomości binarnych.</span><span class="sxs-lookup"><span data-stu-id="04433-155">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04433-156">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="04433-156">See also</span></span>

- <xref:System.ServiceModel.NetTcpSecurity>
- <xref:System.ServiceModel.NetTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="04433-157">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="04433-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="04433-158">Powiązania</span><span class="sxs-lookup"><span data-stu-id="04433-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="04433-159">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="04433-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="04433-160">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="04433-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
