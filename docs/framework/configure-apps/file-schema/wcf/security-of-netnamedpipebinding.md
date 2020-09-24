---
title: <security> dla <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 1a231a60d29cc6a4460de69a98753c23c0386027
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170041"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="17ccd-102">\<security> dla \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="17ccd-102">\<security> of \<netNamedPipeBinding></span></span>

<span data-ttu-id="17ccd-103">Definiuje ustawienia zabezpieczeń dla powiązania.</span><span class="sxs-lookup"><span data-stu-id="17ccd-103">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="17ccd-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="17ccd-104">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17ccd-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="17ccd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="17ccd-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="17ccd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17ccd-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="17ccd-107">Attributes</span></span>  
  
|<span data-ttu-id="17ccd-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="17ccd-108">Attribute</span></span>|<span data-ttu-id="17ccd-109">Opis</span><span class="sxs-lookup"><span data-stu-id="17ccd-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="17ccd-110">tryb</span><span class="sxs-lookup"><span data-stu-id="17ccd-110">mode</span></span>|<span data-ttu-id="17ccd-111">Określa typ zabezpieczeń, które są stosowane do tego powiązania.</span><span class="sxs-lookup"><span data-stu-id="17ccd-111">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="17ccd-112">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="17ccd-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="17ccd-113">-Brak: spowoduje to wyłączenie zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="17ccd-113">-   None: This disables security.</span></span><br /><span data-ttu-id="17ccd-114">-Transport: zabezpieczenia są udostępniane przy użyciu podstawowych zabezpieczeń opartych na transportach.</span><span class="sxs-lookup"><span data-stu-id="17ccd-114">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="17ccd-115">Istnieje możliwość kontrolowania poziomu ochrony w tym trybie.</span><span class="sxs-lookup"><span data-stu-id="17ccd-115">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="17ccd-116">— Wartość domyślna to transport.</span><span class="sxs-lookup"><span data-stu-id="17ccd-116">-   The default value is Transport.</span></span> <span data-ttu-id="17ccd-117">Ten atrybut jest typu <xref:System.ServiceModel.NetNamedPipeSecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="17ccd-117">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17ccd-118">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="17ccd-118">Child Elements</span></span>  
  
|<span data-ttu-id="17ccd-119">Element</span><span class="sxs-lookup"><span data-stu-id="17ccd-119">Element</span></span>|<span data-ttu-id="17ccd-120">Opis</span><span class="sxs-lookup"><span data-stu-id="17ccd-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17ccd-121">transport</span><span class="sxs-lookup"><span data-stu-id="17ccd-121">transport</span></span>|<span data-ttu-id="17ccd-122">Definiuje ustawienia zabezpieczeń transportu.</span><span class="sxs-lookup"><span data-stu-id="17ccd-122">Defines the security settings for the transport.</span></span> <span data-ttu-id="17ccd-123">Ten element jest typu <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement> .</span><span class="sxs-lookup"><span data-stu-id="17ccd-123">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="17ccd-124">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="17ccd-124">Parent Elements</span></span>  
  
|<span data-ttu-id="17ccd-125">Element</span><span class="sxs-lookup"><span data-stu-id="17ccd-125">Element</span></span>|<span data-ttu-id="17ccd-126">Opis</span><span class="sxs-lookup"><span data-stu-id="17ccd-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17ccd-127">powiązanie</span><span class="sxs-lookup"><span data-stu-id="17ccd-127">binding</span></span>|<span data-ttu-id="17ccd-128">Element Binding elementu [\<netNamedPipeBinding>](netnamedpipebinding.md) .</span><span class="sxs-lookup"><span data-stu-id="17ccd-128">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17ccd-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="17ccd-129">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="17ccd-130">Zabezpieczanie usług i klientów</span><span class="sxs-lookup"><span data-stu-id="17ccd-130">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="17ccd-131">Wybieranie typu poświadczeń</span><span class="sxs-lookup"><span data-stu-id="17ccd-131">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="17ccd-132">Powiązania</span><span class="sxs-lookup"><span data-stu-id="17ccd-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="17ccd-133">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="17ccd-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="17ccd-134">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="17ccd-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
