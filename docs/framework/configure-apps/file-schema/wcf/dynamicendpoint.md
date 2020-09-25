---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 6f9cb127deb5651ed27a0ef5802512fb5b6c7b54
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190101"
---
# \<dynamicEndpoint>

<span data-ttu-id="7d896-101">Ten element konfiguracji definiuje standardowy punkt końcowy, który zawiera informacje umożliwiające aplikacji działanie jako program kliencki, który może znaleźć adres punktu końcowego dynamicznie w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="7d896-101">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="7d896-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="7d896-102">Syntax</span></span>  
  
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
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d896-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="7d896-103">Attributes and Elements</span></span>  

 <span data-ttu-id="7d896-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="7d896-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d896-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="7d896-105">Attributes</span></span>  

 <span data-ttu-id="7d896-106">Brak.</span><span class="sxs-lookup"><span data-stu-id="7d896-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7d896-107">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="7d896-107">Child Elements</span></span>  
  
|<span data-ttu-id="7d896-108">Element</span><span class="sxs-lookup"><span data-stu-id="7d896-108">Element</span></span>|<span data-ttu-id="7d896-109">Opis</span><span class="sxs-lookup"><span data-stu-id="7d896-109">Description</span></span>|  
|-------------|-----------------|  
|[\<discoveryClientSettings>](discoveryclientsettings.md)|<span data-ttu-id="7d896-110">Zawiera ustawienia wymagane przez aplikację do uczestnictwa w procesie odnajdowania usług jako klient.</span><span class="sxs-lookup"><span data-stu-id="7d896-110">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d896-111">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="7d896-111">Parent Elements</span></span>  
  
|<span data-ttu-id="7d896-112">Element</span><span class="sxs-lookup"><span data-stu-id="7d896-112">Element</span></span>|<span data-ttu-id="7d896-113">Opis</span><span class="sxs-lookup"><span data-stu-id="7d896-113">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="7d896-114">Kolekcja standardowych punktów końcowych, które są wstępnie zdefiniowanymi punktami końcowymi z co najmniej jedną z jej właściwości (adres, powiązanie, kontrakt).</span><span class="sxs-lookup"><span data-stu-id="7d896-114">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d896-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7d896-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
