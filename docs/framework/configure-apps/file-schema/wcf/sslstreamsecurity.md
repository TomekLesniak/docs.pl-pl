---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: aa6bc7f5a94afc8a190d3d9d2d71ea8b38d8c25b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153576"
---
# \<sslStreamSecurity>

<span data-ttu-id="01e15-101">Reprezentuje element niestandardowego powiązania, który obsługuje zabezpieczenia kanału przy użyciu strumienia SSL.</span><span class="sxs-lookup"><span data-stu-id="01e15-101">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="01e15-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="01e15-102">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01e15-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="01e15-103">Attributes and Elements</span></span>  

 <span data-ttu-id="01e15-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="01e15-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01e15-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="01e15-105">Attributes</span></span>  
  
|<span data-ttu-id="01e15-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="01e15-106">Attribute</span></span>|<span data-ttu-id="01e15-107">Opis</span><span class="sxs-lookup"><span data-stu-id="01e15-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01e15-108">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="01e15-108">requireClientCertificate</span></span>|<span data-ttu-id="01e15-109">Wartość logiczna określająca, czy certyfikat klienta jest wymagany dla tego powiązania.</span><span class="sxs-lookup"><span data-stu-id="01e15-109">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="01e15-110">Wartość domyślna to `false`.</span><span class="sxs-lookup"><span data-stu-id="01e15-110">The default is `false`.</span></span>|  
|<span data-ttu-id="01e15-111">SslProtocols określająca</span><span class="sxs-lookup"><span data-stu-id="01e15-111">sslProtocols</span></span>|<span data-ttu-id="01e15-112">Wartość flagi wyliczenia SslProtocols określająca, która określa, które SslProtocols określająca są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="01e15-112">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="01e15-113">Wartość domyślna to Ssl3&#124;TLS&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="01e15-113">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01e15-114">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="01e15-114">Child Elements</span></span>  

 <span data-ttu-id="01e15-115">Brak.</span><span class="sxs-lookup"><span data-stu-id="01e15-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01e15-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="01e15-116">Parent Elements</span></span>  
  
|<span data-ttu-id="01e15-117">Element</span><span class="sxs-lookup"><span data-stu-id="01e15-117">Element</span></span>|<span data-ttu-id="01e15-118">Opis</span><span class="sxs-lookup"><span data-stu-id="01e15-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="01e15-119">Definiuje wszystkie możliwości powiązań niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="01e15-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01e15-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="01e15-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="01e15-121">Powiązania</span><span class="sxs-lookup"><span data-stu-id="01e15-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="01e15-122">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="01e15-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="01e15-123">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="01e15-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
