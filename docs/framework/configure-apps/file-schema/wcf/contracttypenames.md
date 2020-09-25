---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: f1626983d34a7b66ee23c3a2d9a3c2107812e136
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175983"
---
# \<contractTypeNames>

<span data-ttu-id="1d01f-101">Sekcja konfiguracji określająca listę nazw typów kontraktów, które są nazwami kontraktów usług, których szukasz, oraz kryteriów zwykle używanych podczas wyszukiwania w usłudze.</span><span class="sxs-lookup"><span data-stu-id="1d01f-101">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="1d01f-102">Jeśli określono więcej niż jedną nazwę kontraktu, odpowiedź będzie zawierać tylko punkty końcowe usługi pasujące do wszystkich umów.</span><span class="sxs-lookup"><span data-stu-id="1d01f-102">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="1d01f-103">Należy pamiętać, że w Windows Communication Foundation (WCF) punkt końcowy może obsługiwać tylko jedną umowę.</span><span class="sxs-lookup"><span data-stu-id="1d01f-103">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<contractTypeNames>**  
  
## <a name="syntax"></a><span data-ttu-id="1d01f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="1d01f-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d01f-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="1d01f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1d01f-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="1d01f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d01f-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="1d01f-107">Attributes</span></span>  

 <span data-ttu-id="1d01f-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="1d01f-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1d01f-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="1d01f-109">Child Elements</span></span>  
  
|<span data-ttu-id="1d01f-110">Element</span><span class="sxs-lookup"><span data-stu-id="1d01f-110">Element</span></span>|<span data-ttu-id="1d01f-111">Opis</span><span class="sxs-lookup"><span data-stu-id="1d01f-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](contracttypenames.md)|<span data-ttu-id="1d01f-112">Nazwa typu kontraktu to właściwość, która odwołuje się do zestawu kryteriów zwykle używanych podczas wyszukiwania usługi.</span><span class="sxs-lookup"><span data-stu-id="1d01f-112">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1d01f-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="1d01f-113">Parent Elements</span></span>  
  
|<span data-ttu-id="1d01f-114">Element</span><span class="sxs-lookup"><span data-stu-id="1d01f-114">Element</span></span>|<span data-ttu-id="1d01f-115">Opis</span><span class="sxs-lookup"><span data-stu-id="1d01f-115">Description</span></span>|  
|-------------|-----------------|  
|[\<findCriteria>](findcriteria.md)|<span data-ttu-id="1d01f-116">Element konfiguracji, który dostarcza zestaw kryteriów używanych przez aplikację kliencką do wyszukiwania usługi odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="1d01f-116">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="1d01f-117">Kryteria mogą być pogrupowane w kryteria wyszukiwania (określające, które usługi są szukane) i znajdować kryteria zakończenia (jak długo wyszukiwanie powinno trwać).</span><span class="sxs-lookup"><span data-stu-id="1d01f-117">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d01f-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1d01f-118">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
