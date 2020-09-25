---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 6e3f273af807eb362f005fef63246013ecc88581
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192246"
---
# \<discoveryClientSettings>

<span data-ttu-id="5bcc0-101">Zawiera ustawienia wymagane przez aplikację do uczestnictwa w procesie odnajdowania usług jako klient.</span><span class="sxs-lookup"><span data-stu-id="5bcc0-101">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="5bcc0-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="5bcc0-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5bcc0-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="5bcc0-103">Attributes and Elements</span></span>  

 <span data-ttu-id="5bcc0-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="5bcc0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5bcc0-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="5bcc0-105">Attributes</span></span>  
  
|<span data-ttu-id="5bcc0-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="5bcc0-106">Attribute</span></span>|<span data-ttu-id="5bcc0-107">Opis</span><span class="sxs-lookup"><span data-stu-id="5bcc0-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5bcc0-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="5bcc0-108">discoveryEndpoint</span></span>|<span data-ttu-id="5bcc0-109">Ciąg zawierający nazwę punktu końcowego odnajdywania, który umożliwia aplikacji klienckiej automatyczne wyszukiwanie usługi wykrywalnej i znajdowanie jej adresu w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="5bcc0-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5bcc0-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="5bcc0-110">Child Elements</span></span>  
  
|<span data-ttu-id="5bcc0-111">Element</span><span class="sxs-lookup"><span data-stu-id="5bcc0-111">Element</span></span>|<span data-ttu-id="5bcc0-112">Opis</span><span class="sxs-lookup"><span data-stu-id="5bcc0-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="5bcc0-113">Element konfiguracji, który dostarcza zestaw kryteriów używanych przez aplikację kliencką do wyszukiwania usługi odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="5bcc0-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="5bcc0-114">Kryteria mogą być pogrupowane w kryteria wyszukiwania (określające, które usługi są szukane) i znajdować kryteria zakończenia (jak długo wyszukiwanie powinno trwać).</span><span class="sxs-lookup"><span data-stu-id="5bcc0-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5bcc0-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="5bcc0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="5bcc0-116">Element</span><span class="sxs-lookup"><span data-stu-id="5bcc0-116">Element</span></span>|<span data-ttu-id="5bcc0-117">Opis</span><span class="sxs-lookup"><span data-stu-id="5bcc0-117">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="5bcc0-118">Definiuje standardowy punkt końcowy, który zawiera informacje umożliwiające aplikacji działanie jako program kliencki, który może znaleźć adres punktu końcowego dynamicznie w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="5bcc0-118">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5bcc0-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5bcc0-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
