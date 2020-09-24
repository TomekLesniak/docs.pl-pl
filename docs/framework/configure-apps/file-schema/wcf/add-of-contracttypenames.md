---
title: <add> dla <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 69a0bbbc8774251dbdc062875bb06453f355c882
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149143"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="57a4a-102">\<add> dla \<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="57a4a-102">\<add> of \<contractTypeNames></span></span>

<span data-ttu-id="57a4a-103">Element konfiguracji, który określa nazwę kontraktu usług, których szukasz, i kryteria zwykle używane podczas wyszukiwania usługi.</span><span class="sxs-lookup"><span data-stu-id="57a4a-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="57a4a-104">Jeśli określono więcej niż jedną nazwę kontraktu, odpowiedź będzie zawierać tylko punkty końcowe usługi pasujące do wszystkich umów.</span><span class="sxs-lookup"><span data-stu-id="57a4a-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="57a4a-105">Należy pamiętać, że w Windows Communication Foundation (WCF) punkt końcowy może obsługiwać tylko jedną umowę.</span><span class="sxs-lookup"><span data-stu-id="57a4a-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="57a4a-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="57a4a-106">Syntax</span></span>  
  
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
              <add name="String" namespace="String" />
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57a4a-107">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="57a4a-107">Attributes and Elements</span></span>  

 <span data-ttu-id="57a4a-108">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="57a4a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57a4a-109">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="57a4a-109">Attributes</span></span>  
  
|<span data-ttu-id="57a4a-110">Atrybut</span><span class="sxs-lookup"><span data-stu-id="57a4a-110">Attribute</span></span>|<span data-ttu-id="57a4a-111">Opis</span><span class="sxs-lookup"><span data-stu-id="57a4a-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="57a4a-112">name</span><span class="sxs-lookup"><span data-stu-id="57a4a-112">name</span></span>|<span data-ttu-id="57a4a-113">Ciąg określający nazwę typu kontraktu.</span><span class="sxs-lookup"><span data-stu-id="57a4a-113">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="57a4a-114">namespace</span><span class="sxs-lookup"><span data-stu-id="57a4a-114">namespace</span></span>|<span data-ttu-id="57a4a-115">Ciąg określający przestrzeń nazw typu kontraktu.</span><span class="sxs-lookup"><span data-stu-id="57a4a-115">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57a4a-116">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="57a4a-116">Child Elements</span></span>  

 <span data-ttu-id="57a4a-117">Brak</span><span class="sxs-lookup"><span data-stu-id="57a4a-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="57a4a-118">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="57a4a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="57a4a-119">Element</span><span class="sxs-lookup"><span data-stu-id="57a4a-119">Element</span></span>|<span data-ttu-id="57a4a-120">Opis</span><span class="sxs-lookup"><span data-stu-id="57a4a-120">Description</span></span>|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|<span data-ttu-id="57a4a-121">Kolekcja nazw typów kontraktu.</span><span class="sxs-lookup"><span data-stu-id="57a4a-121">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57a4a-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="57a4a-122">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
