---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: adfd94365ceb0ddc3164a6baef838c16027b4bc3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190141"
---
# \<dns>

<span data-ttu-id="a973c-101">Określa oczekiwaną tożsamość serwera.</span><span class="sxs-lookup"><span data-stu-id="a973c-101">Specifies the expected identity of the server.</span></span> <span data-ttu-id="a973c-102">Ta tożsamość jest prawidłowa dla trybu uwierzytelniania certyfikatu x509, jeśli certyfikat serwera zawiera system DNS o tej samej wartości.</span><span class="sxs-lookup"><span data-stu-id="a973c-102">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="a973c-103">Obowiązuje również w przypadku trybu uwierzytelniania systemu Windows, jeśli nazwa SPN ma taką samą wartość.</span><span class="sxs-lookup"><span data-stu-id="a973c-103">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="a973c-104">Aby uzyskać więcej informacji na temat ustawiania wartości elementu, zobacz [tożsamość usługi i uwierzytelnianie](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="a973c-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**  
  
## <a name="syntax"></a><span data-ttu-id="a973c-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="a973c-105">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a973c-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="a973c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a973c-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="a973c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a973c-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="a973c-108">Attributes</span></span>  
  
|<span data-ttu-id="a973c-109">Atrybut</span><span class="sxs-lookup"><span data-stu-id="a973c-109">Attribute</span></span>|<span data-ttu-id="a973c-110">Opis</span><span class="sxs-lookup"><span data-stu-id="a973c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a973c-111">wartość</span><span class="sxs-lookup"><span data-stu-id="a973c-111">value</span></span>|<span data-ttu-id="a973c-112">Serwer DNS certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="a973c-112">The DNS of the certificate.</span></span> <span data-ttu-id="a973c-113">DNS to standardowy branżowy protokół używany do lokalizowania komputerów w sieci opartej na protokole IP.</span><span class="sxs-lookup"><span data-stu-id="a973c-113">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="a973c-114">Użytkownicy mogą pamiętać nazwy wyświetlane, takie jak `https://go.microsoft.com/fwlink/?prd=10929` lub `https://go.microsoft.com/fwlink/?LinkID=96165` , łatwiejsze niż adresy oparte na liczbie, takie jak 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="a973c-114">Users can remember display names, such as `https://go.microsoft.com/fwlink/?prd=10929` or `https://go.microsoft.com/fwlink/?LinkID=96165`, easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a973c-115">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="a973c-115">Child Elements</span></span>  

 <span data-ttu-id="a973c-116">Brak.</span><span class="sxs-lookup"><span data-stu-id="a973c-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a973c-117">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="a973c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a973c-118">Element</span><span class="sxs-lookup"><span data-stu-id="a973c-118">Element</span></span>|<span data-ttu-id="a973c-119">Opis</span><span class="sxs-lookup"><span data-stu-id="a973c-119">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="a973c-120">Określa tożsamość usługi do uwierzytelnienia przez klienta.</span><span class="sxs-lookup"><span data-stu-id="a973c-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a973c-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="a973c-121">Example</span></span>  

 <span data-ttu-id="a973c-122">Poniższy kod konfiguracji określa DNS certyfikatu X. 509, który jest używany do uwierzytelniania serwera.</span><span class="sxs-lookup"><span data-stu-id="a973c-122">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="a973c-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a973c-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="a973c-124">Uwierzytelnianie i tożsamość usług</span><span class="sxs-lookup"><span data-stu-id="a973c-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
