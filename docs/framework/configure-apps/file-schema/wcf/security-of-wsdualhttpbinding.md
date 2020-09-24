---
title: <security> dla <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 7398cd538bb240e78413575f7c28abe7f797d05c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162208"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="fe001-102">\<security> dla \<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="fe001-102">\<security> of \<wsDualHttpBinding></span></span>

<span data-ttu-id="fe001-103">Definiuje możliwości zabezpieczeń programu [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="fe001-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="fe001-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fe001-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe001-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="fe001-105">Attributes and Elements</span></span>  

 <span data-ttu-id="fe001-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="fe001-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe001-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="fe001-107">Attributes</span></span>  
  
|<span data-ttu-id="fe001-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="fe001-108">Attribute</span></span>|<span data-ttu-id="fe001-109">Opis</span><span class="sxs-lookup"><span data-stu-id="fe001-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe001-110">tryb</span><span class="sxs-lookup"><span data-stu-id="fe001-110">mode</span></span>|<span data-ttu-id="fe001-111">Obowiązkowe.</span><span class="sxs-lookup"><span data-stu-id="fe001-111">-   Optional.</span></span> <span data-ttu-id="fe001-112">Określa typ stosowanego zabezpieczenia.</span><span class="sxs-lookup"><span data-stu-id="fe001-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="fe001-113">Wartość domyślna to `Message`.</span><span class="sxs-lookup"><span data-stu-id="fe001-113">The default value is `Message`.</span></span> <span data-ttu-id="fe001-114">Ten atrybut jest typu <xref:System.ServiceModel.WSDualHttpSecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="fe001-114">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="fe001-115">Atrybut Mode</span><span class="sxs-lookup"><span data-stu-id="fe001-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="fe001-116">Wartość</span><span class="sxs-lookup"><span data-stu-id="fe001-116">Value</span></span>|<span data-ttu-id="fe001-117">Opis</span><span class="sxs-lookup"><span data-stu-id="fe001-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fe001-118">Brak</span><span class="sxs-lookup"><span data-stu-id="fe001-118">None</span></span>|<span data-ttu-id="fe001-119">Zabezpieczenia są wyłączone.</span><span class="sxs-lookup"><span data-stu-id="fe001-119">Security is disabled.</span></span>|  
|<span data-ttu-id="fe001-120">Wiadomość</span><span class="sxs-lookup"><span data-stu-id="fe001-120">Message</span></span>|<span data-ttu-id="fe001-121">Zabezpieczenia są udostępniane przy użyciu zabezpieczeń komunikatów protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="fe001-121">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe001-122">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="fe001-122">Child Elements</span></span>  
  
|<span data-ttu-id="fe001-123">Element</span><span class="sxs-lookup"><span data-stu-id="fe001-123">Element</span></span>|<span data-ttu-id="fe001-124">Opis</span><span class="sxs-lookup"><span data-stu-id="fe001-124">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="fe001-125">Definiuje ustawienia zabezpieczeń na poziomie wiadomości.</span><span class="sxs-lookup"><span data-stu-id="fe001-125">Defines the settings for the message-level security.</span></span> <span data-ttu-id="fe001-126">Ten element jest typu <xref:System.ServiceModel.MessageSecurityOverHttp> .</span><span class="sxs-lookup"><span data-stu-id="fe001-126">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fe001-127">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="fe001-127">Parent Elements</span></span>  
  
|<span data-ttu-id="fe001-128">Element</span><span class="sxs-lookup"><span data-stu-id="fe001-128">Element</span></span>|<span data-ttu-id="fe001-129">Opis</span><span class="sxs-lookup"><span data-stu-id="fe001-129">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="fe001-130">Definiuje wszystkie możliwości powiązań [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="fe001-130">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe001-131">Uwagi</span><span class="sxs-lookup"><span data-stu-id="fe001-131">Remarks</span></span>  

 <span data-ttu-id="fe001-132">Podwójne powiązanie uwidacznia adres IP klienta w usłudze.</span><span class="sxs-lookup"><span data-stu-id="fe001-132">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="fe001-133">Klient powinien korzystać z zabezpieczeń, aby upewnić się, że tylko nawiązuje połączenie z usługami, które ufają.</span><span class="sxs-lookup"><span data-stu-id="fe001-133">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe001-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fe001-134">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="fe001-135">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="fe001-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="fe001-136">Powiązania</span><span class="sxs-lookup"><span data-stu-id="fe001-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fe001-137">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="fe001-137">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="fe001-138">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="fe001-138">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
