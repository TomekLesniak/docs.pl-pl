---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: af9cf127652f1e12ae57948f9b4a6a26285af793
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192259"
---
# \<discoveryClient>

<span data-ttu-id="623fe-101">Element konfiguracji do tworzenia niestandardowego powiązania, które umożliwia aplikacji klienckiej automatyczne wyszukiwanie usługi wykrywalnej i znajdowanie jej adresu w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="623fe-101">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**  
  
## <a name="syntax"></a><span data-ttu-id="623fe-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="623fe-102">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="623fe-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="623fe-103">Attributes and Elements</span></span>  

 <span data-ttu-id="623fe-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="623fe-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="623fe-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="623fe-105">Attributes</span></span>  
  
|<span data-ttu-id="623fe-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="623fe-106">Attribute</span></span>|<span data-ttu-id="623fe-107">Opis</span><span class="sxs-lookup"><span data-stu-id="623fe-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="623fe-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="623fe-108">discoveryEndpoint</span></span>|<span data-ttu-id="623fe-109">Ciąg zawierający nazwę punktu końcowego odnajdywania, który umożliwia aplikacji klienckiej automatyczne wyszukiwanie usługi wykrywalnej i znajdowanie jej adresu w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="623fe-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="623fe-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="623fe-110">Child Elements</span></span>  
  
|<span data-ttu-id="623fe-111">Element</span><span class="sxs-lookup"><span data-stu-id="623fe-111">Element</span></span>|<span data-ttu-id="623fe-112">Opis</span><span class="sxs-lookup"><span data-stu-id="623fe-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="623fe-113">Element konfiguracji, który dostarcza zestaw kryteriów używanych przez aplikację kliencką do wyszukiwania usługi odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="623fe-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="623fe-114">Kryteria mogą być pogrupowane w kryteria wyszukiwania (określające, które usługi są szukane) i znajdować kryteria zakończenia (jak długo wyszukiwanie powinno trwać).</span><span class="sxs-lookup"><span data-stu-id="623fe-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="623fe-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="623fe-115">Parent Elements</span></span>  
  
|<span data-ttu-id="623fe-116">Element</span><span class="sxs-lookup"><span data-stu-id="623fe-116">Element</span></span>|<span data-ttu-id="623fe-117">Opis</span><span class="sxs-lookup"><span data-stu-id="623fe-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="623fe-118">Definiuje wszystkie możliwości powiązań niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="623fe-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="623fe-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="623fe-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
