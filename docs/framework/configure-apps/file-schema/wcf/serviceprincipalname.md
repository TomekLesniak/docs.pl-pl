---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 0d03844a58de5b4af93f276de75c88af6efed3f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153797"
---
# \<servicePrincipalName>

<span data-ttu-id="dbf36-101">Określa tożsamość usługi za pomocą nazwy głównej usługi (SPN).</span><span class="sxs-lookup"><span data-stu-id="dbf36-101">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="dbf36-102">Aby uzyskać więcej informacji na temat ustawiania nazwy SPN, zobacz [tożsamość usługi i uwierzytelnianie](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="dbf36-102">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="dbf36-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="dbf36-103">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbf36-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="dbf36-104">Attributes and Elements</span></span>  

 <span data-ttu-id="dbf36-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="dbf36-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbf36-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="dbf36-106">Attributes</span></span>  
  
|<span data-ttu-id="dbf36-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="dbf36-107">Attribute</span></span>|<span data-ttu-id="dbf36-108">Opis</span><span class="sxs-lookup"><span data-stu-id="dbf36-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dbf36-109">wartość</span><span class="sxs-lookup"><span data-stu-id="dbf36-109">value</span></span>|<span data-ttu-id="dbf36-110">Nazwa, przez którą klient jednoznacznie identyfikuje wystąpienie usługi.</span><span class="sxs-lookup"><span data-stu-id="dbf36-110">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="dbf36-111">W przypadku instalowania wielu wystąpień usługi na komputerach w lesie, każde wystąpienie musi mieć własną nazwę SPN.</span><span class="sxs-lookup"><span data-stu-id="dbf36-111">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="dbf36-112">Dana nazwa wystąpienia usługi może mieć wiele nazw SPN, jeśli istnieje wiele nazwy, których klienci mogą używać na potrzeby uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="dbf36-112">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dbf36-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="dbf36-113">Child Elements</span></span>  

 <span data-ttu-id="dbf36-114">Brak.</span><span class="sxs-lookup"><span data-stu-id="dbf36-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dbf36-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="dbf36-115">Parent Elements</span></span>  
  
|<span data-ttu-id="dbf36-116">Element</span><span class="sxs-lookup"><span data-stu-id="dbf36-116">Element</span></span>|<span data-ttu-id="dbf36-117">Opis</span><span class="sxs-lookup"><span data-stu-id="dbf36-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="dbf36-118">Określa tożsamość usługi do uwierzytelnienia przez klienta.</span><span class="sxs-lookup"><span data-stu-id="dbf36-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbf36-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="dbf36-119">Remarks</span></span>  

 <span data-ttu-id="dbf36-120">Bezpieczny Windows Communication Foundation (WCF), który nawiązuje połączenie z punktem końcowym z tą tożsamością używa nazwy SPN podczas uwierzytelniania SSPI przy użyciu punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="dbf36-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf36-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dbf36-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="dbf36-122">Uwierzytelnianie i tożsamość usług</span><span class="sxs-lookup"><span data-stu-id="dbf36-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
