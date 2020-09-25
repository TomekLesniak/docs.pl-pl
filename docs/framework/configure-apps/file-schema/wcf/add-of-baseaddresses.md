---
title: <add> dla <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: cd0ef5cc5f0f809bdafa23bd312e7e30fcdccc21
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181612"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="96e2d-102">\<add> dla \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="96e2d-102">\<add> of \<baseAddresses></span></span>

<span data-ttu-id="96e2d-103">Reprezentuje element konfiguracji, który określa adresy podstawowe używane przez hosta usługi.</span><span class="sxs-lookup"><span data-stu-id="96e2d-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="96e2d-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="96e2d-104">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="96e2d-105">Typ</span><span class="sxs-lookup"><span data-stu-id="96e2d-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96e2d-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="96e2d-106">Attributes and Elements</span></span>  

 <span data-ttu-id="96e2d-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="96e2d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96e2d-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="96e2d-108">Attributes</span></span>  
  
|<span data-ttu-id="96e2d-109">Atrybut</span><span class="sxs-lookup"><span data-stu-id="96e2d-109">Attribute</span></span>|<span data-ttu-id="96e2d-110">Opis</span><span class="sxs-lookup"><span data-stu-id="96e2d-110">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="96e2d-111">Ciąg określający adres podstawowy używany przez hosta usługi.</span><span class="sxs-lookup"><span data-stu-id="96e2d-111">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96e2d-112">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="96e2d-112">Child Elements</span></span>  

 <span data-ttu-id="96e2d-113">Brak.</span><span class="sxs-lookup"><span data-stu-id="96e2d-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96e2d-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="96e2d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="96e2d-115">Element</span><span class="sxs-lookup"><span data-stu-id="96e2d-115">Element</span></span>|<span data-ttu-id="96e2d-116">Opis</span><span class="sxs-lookup"><span data-stu-id="96e2d-116">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="96e2d-117">Kolekcja `baseAddress` elementów.</span><span class="sxs-lookup"><span data-stu-id="96e2d-117">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96e2d-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="96e2d-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="96e2d-119">Hosting</span><span class="sxs-lookup"><span data-stu-id="96e2d-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
