---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 63f46753da13469147b378f373de9888a007bf52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162221"
---
# \<scopes>

<span data-ttu-id="153bf-101">Zawiera kolekcję elementów konfiguracji, które określają niestandardowe identyfikatory URI, których można użyć do filtrowania punktów końcowych usługi podczas zapytania.</span><span class="sxs-lookup"><span data-stu-id="153bf-101">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**  
  
## <a name="syntax"></a><span data-ttu-id="153bf-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="153bf-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="153bf-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="153bf-103">Attributes and Elements</span></span>  

 <span data-ttu-id="153bf-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="153bf-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="153bf-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="153bf-105">Attributes</span></span>  

 <span data-ttu-id="153bf-106">Brak.</span><span class="sxs-lookup"><span data-stu-id="153bf-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="153bf-107">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="153bf-107">Child Elements</span></span>  
  
|<span data-ttu-id="153bf-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="153bf-108">Attribute</span></span>|<span data-ttu-id="153bf-109">Opis</span><span class="sxs-lookup"><span data-stu-id="153bf-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-scopes.md)|<span data-ttu-id="153bf-110">Dodaje informacje o zakresie dla punktu końcowego, którego można użyć w kryterium dopasowywania w celu znalezienia usług.</span><span class="sxs-lookup"><span data-stu-id="153bf-110">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="153bf-111">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="153bf-111">Parent Elements</span></span>  
  
|<span data-ttu-id="153bf-112">Element</span><span class="sxs-lookup"><span data-stu-id="153bf-112">Element</span></span>|<span data-ttu-id="153bf-113">Opis</span><span class="sxs-lookup"><span data-stu-id="153bf-113">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="153bf-114">Określa różne ustawienia odnajdywania dla punktu końcowego, takie jak jego wykrywalność, zakresy i wszelkie niestandardowe rozszerzenia do swoich metadanych.</span><span class="sxs-lookup"><span data-stu-id="153bf-114">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="153bf-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="153bf-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
