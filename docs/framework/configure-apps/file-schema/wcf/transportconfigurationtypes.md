---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 6545e1f1be2695d165b89a38c7218e0acdc88bfc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162026"
---
# \<transportConfigurationTypes>

<span data-ttu-id="57462-101">Reprezentuje kolekcję elementów konfiguracji, które identyfikują typ określonego transportu.</span><span class="sxs-lookup"><span data-stu-id="57462-101">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="57462-102">Można go użyć do dodania niestandardowych protokołów WAS.</span><span class="sxs-lookup"><span data-stu-id="57462-102">This can be used to add custom WAS protocols.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="57462-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="57462-103">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57462-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="57462-104">Attributes and Elements</span></span>  

 <span data-ttu-id="57462-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="57462-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57462-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="57462-106">Attributes</span></span>  
  
|<span data-ttu-id="57462-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="57462-107">Attribute</span></span>|<span data-ttu-id="57462-108">Opis</span><span class="sxs-lookup"><span data-stu-id="57462-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="57462-109">name</span><span class="sxs-lookup"><span data-stu-id="57462-109">name</span></span>|<span data-ttu-id="57462-110">Nazwa transportu</span><span class="sxs-lookup"><span data-stu-id="57462-110">The name of the transport</span></span>|  
|<span data-ttu-id="57462-111">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="57462-111">transportConfigurationType</span></span>|<span data-ttu-id="57462-112">Typ implementujący transport</span><span class="sxs-lookup"><span data-stu-id="57462-112">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57462-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="57462-113">Child Elements</span></span>  
  
|<span data-ttu-id="57462-114">Element</span><span class="sxs-lookup"><span data-stu-id="57462-114">Element</span></span>|<span data-ttu-id="57462-115">Opis</span><span class="sxs-lookup"><span data-stu-id="57462-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-transportconfigurationtype.md)|<span data-ttu-id="57462-116">Dodaje element konfiguracji, który identyfikuje typ określonego transportu.</span><span class="sxs-lookup"><span data-stu-id="57462-116">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="57462-117">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="57462-117">Parent Elements</span></span>  
  
|<span data-ttu-id="57462-118">Element</span><span class="sxs-lookup"><span data-stu-id="57462-118">Element</span></span>|<span data-ttu-id="57462-119">Opis</span><span class="sxs-lookup"><span data-stu-id="57462-119">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="57462-120">Definiuje typ tworzenia wystąpień środowiska hostingu usługi dla określonego transportu.</span><span class="sxs-lookup"><span data-stu-id="57462-120">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57462-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="57462-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="57462-122">Hosting</span><span class="sxs-lookup"><span data-stu-id="57462-122">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
