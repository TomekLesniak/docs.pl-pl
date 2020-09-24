---
title: <transport> dla <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 60e8758d653848176ca3f287e253bd7990e78470
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162052"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="9301b-102">\<transport> dla \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="9301b-102">\<transport> of \<ws2007HttpBinding></span></span>

<span data-ttu-id="9301b-103">Definiuje ustawienia uwierzytelniania dla transportu HTTP.</span><span class="sxs-lookup"><span data-stu-id="9301b-103">Defines authentication settings for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="9301b-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9301b-104">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="9301b-105">Typ</span><span class="sxs-lookup"><span data-stu-id="9301b-105">Type</span></span>  

 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9301b-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="9301b-106">Attributes and Elements</span></span>  

 <span data-ttu-id="9301b-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="9301b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9301b-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="9301b-108">Attributes</span></span>  
  
|<span data-ttu-id="9301b-109">Atrybut</span><span class="sxs-lookup"><span data-stu-id="9301b-109">Attribute</span></span>|<span data-ttu-id="9301b-110">Opis</span><span class="sxs-lookup"><span data-stu-id="9301b-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="9301b-111">Określa poświadczenie używane do uwierzytelniania klienta w usłudze.</span><span class="sxs-lookup"><span data-stu-id="9301b-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="9301b-112">Ten atrybut jest typu <xref:System.ServiceModel.HttpClientCredentialType> .</span><span class="sxs-lookup"><span data-stu-id="9301b-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="9301b-113">Określa poświadczenie używane do uwierzytelniania klienta programu na serwerze proxy domeny.</span><span class="sxs-lookup"><span data-stu-id="9301b-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="9301b-114">Ten atrybut jest typu <xref:System.ServiceModel.HttpProxyCredentialType> .</span><span class="sxs-lookup"><span data-stu-id="9301b-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="9301b-115">Obszar uwierzytelniania dla uwierzytelniania szyfrowanego lub podstawowego.</span><span class="sxs-lookup"><span data-stu-id="9301b-115">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="9301b-116">Wartość domyślna to pusty ciąg.</span><span class="sxs-lookup"><span data-stu-id="9301b-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="9301b-117">Obszar uwierzytelniania określa co najmniej nazwę hosta, który wykonuje uwierzytelnianie.</span><span class="sxs-lookup"><span data-stu-id="9301b-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="9301b-118">Można również określić kolekcję użytkowników, którzy mają dostęp.</span><span class="sxs-lookup"><span data-stu-id="9301b-118">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="9301b-119">Użytkownik może wysyłać zapytania do obszaru uwierzytelniania, aby określić, która z kilku możliwych nazw użytkowników i haseł może być używana.</span><span class="sxs-lookup"><span data-stu-id="9301b-119">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="9301b-120">clientCredentialtype — atrybut</span><span class="sxs-lookup"><span data-stu-id="9301b-120">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9301b-121">Wartość</span><span class="sxs-lookup"><span data-stu-id="9301b-121">Value</span></span>|<span data-ttu-id="9301b-122">Opis</span><span class="sxs-lookup"><span data-stu-id="9301b-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9301b-123">Brak</span><span class="sxs-lookup"><span data-stu-id="9301b-123">None</span></span>|<span data-ttu-id="9301b-124">Zabezpieczenia są wyłączone.</span><span class="sxs-lookup"><span data-stu-id="9301b-124">Security is disabled.</span></span>|  
|<span data-ttu-id="9301b-125">Podstawowy</span><span class="sxs-lookup"><span data-stu-id="9301b-125">Basic</span></span>|<span data-ttu-id="9301b-126">Używa uwierzytelniania podstawowego.</span><span class="sxs-lookup"><span data-stu-id="9301b-126">Uses basic authentication.</span></span>|  
|<span data-ttu-id="9301b-127">Szyfrowane</span><span class="sxs-lookup"><span data-stu-id="9301b-127">Digest</span></span>|<span data-ttu-id="9301b-128">Używa uwierzytelniania szyfrowanego.</span><span class="sxs-lookup"><span data-stu-id="9301b-128">Uses digest authentication.</span></span>|  
|<span data-ttu-id="9301b-129">NTLM</span><span class="sxs-lookup"><span data-stu-id="9301b-129">Ntlm</span></span>|<span data-ttu-id="9301b-130">Używa uwierzytelniania NTLM jako rezerwy z domeną systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="9301b-130">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="9301b-131">Windows</span><span class="sxs-lookup"><span data-stu-id="9301b-131">Windows</span></span>|<span data-ttu-id="9301b-132">Używa zintegrowanego uwierzytelniania systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="9301b-132">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="9301b-133">Certyfikat</span><span class="sxs-lookup"><span data-stu-id="9301b-133">Certificate</span></span>|<span data-ttu-id="9301b-134">Uwierzytelnia klienta za pomocą certyfikatów X. 509.</span><span class="sxs-lookup"><span data-stu-id="9301b-134">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="9301b-135">proxyCredentialType — atrybut</span><span class="sxs-lookup"><span data-stu-id="9301b-135">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9301b-136">Wartość</span><span class="sxs-lookup"><span data-stu-id="9301b-136">Value</span></span>|<span data-ttu-id="9301b-137">Opis</span><span class="sxs-lookup"><span data-stu-id="9301b-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9301b-138">Brak</span><span class="sxs-lookup"><span data-stu-id="9301b-138">None</span></span>|<span data-ttu-id="9301b-139">Zabezpieczenia są wyłączone.</span><span class="sxs-lookup"><span data-stu-id="9301b-139">Security is disabled.</span></span>|  
|<span data-ttu-id="9301b-140">Podstawowy</span><span class="sxs-lookup"><span data-stu-id="9301b-140">Basic</span></span>|<span data-ttu-id="9301b-141">Używa uwierzytelniania podstawowego.</span><span class="sxs-lookup"><span data-stu-id="9301b-141">Uses basic authentication.</span></span>|  
|<span data-ttu-id="9301b-142">Szyfrowane</span><span class="sxs-lookup"><span data-stu-id="9301b-142">Digest</span></span>|<span data-ttu-id="9301b-143">Używa uwierzytelniania szyfrowanego.</span><span class="sxs-lookup"><span data-stu-id="9301b-143">Uses digest authentication.</span></span>|  
|<span data-ttu-id="9301b-144">NTLM</span><span class="sxs-lookup"><span data-stu-id="9301b-144">Ntlm</span></span>|<span data-ttu-id="9301b-145">Używa protokołu NTLM jako rezerwy z domeną systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="9301b-145">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="9301b-146">Windows</span><span class="sxs-lookup"><span data-stu-id="9301b-146">Windows</span></span>|<span data-ttu-id="9301b-147">Używa zintegrowanego uwierzytelniania systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="9301b-147">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="9301b-148">Certyfikat</span><span class="sxs-lookup"><span data-stu-id="9301b-148">Certificate</span></span>|<span data-ttu-id="9301b-149">Uwierzytelnia klienta za pomocą certyfikatów X. 509.</span><span class="sxs-lookup"><span data-stu-id="9301b-149">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9301b-150">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="9301b-150">Child Elements</span></span>  

 <span data-ttu-id="9301b-151">Brak</span><span class="sxs-lookup"><span data-stu-id="9301b-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9301b-152">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="9301b-152">Parent Elements</span></span>  
  
|<span data-ttu-id="9301b-153">Element</span><span class="sxs-lookup"><span data-stu-id="9301b-153">Element</span></span>|<span data-ttu-id="9301b-154">Opis</span><span class="sxs-lookup"><span data-stu-id="9301b-154">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|<span data-ttu-id="9301b-155">Reprezentuje możliwości zabezpieczeń [\<ws2007HttpBinding>](ws2007httpbinding.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="9301b-155">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9301b-156">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9301b-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="9301b-157">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="9301b-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9301b-158">Powiązania</span><span class="sxs-lookup"><span data-stu-id="9301b-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9301b-159">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="9301b-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9301b-160">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="9301b-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
