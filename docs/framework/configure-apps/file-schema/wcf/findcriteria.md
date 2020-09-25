---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: ce2b1fdd85e0454f901bac393e2f44ae0c6da43f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178150"
---
# \<findCriteria>

<span data-ttu-id="968bd-101">Element konfiguracji, który dostarcza zestaw kryteriów używanych przez aplikację kliencką do wyszukiwania usługi odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="968bd-101">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="968bd-102">Kryteria mogą być pogrupowane w kryteria wyszukiwania (określające, które usługi są szukane) i znajdować kryteria zakończenia (jak długo wyszukiwanie powinno trwać).</span><span class="sxs-lookup"><span data-stu-id="968bd-102">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<findCriteria>**  
  
## <a name="syntax"></a><span data-ttu-id="968bd-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="968bd-103">Syntax</span></span>  
  
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
            </contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="968bd-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="968bd-104">Attributes and Elements</span></span>  

 <span data-ttu-id="968bd-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="968bd-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="968bd-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="968bd-106">Attributes</span></span>  
  
|<span data-ttu-id="968bd-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="968bd-107">Attribute</span></span>|<span data-ttu-id="968bd-108">Opis</span><span class="sxs-lookup"><span data-stu-id="968bd-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="968bd-109">czas trwania</span><span class="sxs-lookup"><span data-stu-id="968bd-109">duration</span></span>|<span data-ttu-id="968bd-110">Wartość TimeSpan, która określa maksymalny czas oczekiwania na odpowiedzi z usług w sieci.</span><span class="sxs-lookup"><span data-stu-id="968bd-110">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="968bd-111">Domyślny czas trwania wynosi 20 sekund.</span><span class="sxs-lookup"><span data-stu-id="968bd-111">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="968bd-112">maxResults</span><span class="sxs-lookup"><span data-stu-id="968bd-112">maxResults</span></span>|<span data-ttu-id="968bd-113">Liczba całkowita określająca maksymalną liczbę odpowiedzi od usług w sieci lub Internetu.</span><span class="sxs-lookup"><span data-stu-id="968bd-113">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="968bd-114">Jeśli zostaną odebrane maksymalne odpowiedzi przed upływem wartości określonej w `duration` atrybucie, kończy się operacja znajdowania.</span><span class="sxs-lookup"><span data-stu-id="968bd-114">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="968bd-115">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="968bd-115">scopeMatchBy</span></span>|<span data-ttu-id="968bd-116">Identyfikator URI, który określa zgodny algorytm do użycia podczas dopasowywania zakresów w komunikacie sondy z tym punktem końcowym.</span><span class="sxs-lookup"><span data-stu-id="968bd-116">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="968bd-117">Istnieją pięć obsługiwanych reguł dopasowania zakresu.</span><span class="sxs-lookup"><span data-stu-id="968bd-117">There are five supported scope-matching rules.</span></span> <span data-ttu-id="968bd-118">Jeśli nie określisz reguły dopasowywania zakresu, `ScopeMatchByPrefix` jest używana.</span><span class="sxs-lookup"><span data-stu-id="968bd-118">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="968bd-119">Aby uzyskać więcej informacji na temat tego, zobacz <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="968bd-119">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="968bd-120">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="968bd-120">Child Elements</span></span>  
  
|<span data-ttu-id="968bd-121">Element</span><span class="sxs-lookup"><span data-stu-id="968bd-121">Element</span></span>|<span data-ttu-id="968bd-122">Opis</span><span class="sxs-lookup"><span data-stu-id="968bd-122">Description</span></span>|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|<span data-ttu-id="968bd-123">Kolekcja elementów konfiguracji, które zawierają nazwy typów kontraktu usługi przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="968bd-123">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="968bd-124">\<extensions> dla \<findCriteria></span><span class="sxs-lookup"><span data-stu-id="968bd-124">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="968bd-125">Kolekcja obiektów elementu XML, które udostępniają rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="968bd-125">A collection of XML element objects that provide extensions.</span></span>|  
|[\<scopes>](scopes.md)|<span data-ttu-id="968bd-126">Kolekcja obiektów, które zawierają bezwzględne identyfikatory URI, które są używane podczas operacji znajdowania do lokalizowania określonej usługi lub usług.</span><span class="sxs-lookup"><span data-stu-id="968bd-126">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="968bd-127">Jeśli określona usługa zostanie znaleziona, nastąpi pomyślne dopasowanie między identyfikatorem URI usługi i identyfikatorem URI zakresu, czasami z pomocą reguł zakresu, które obsługują komplikacje dopasowywania.</span><span class="sxs-lookup"><span data-stu-id="968bd-127">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="968bd-128">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="968bd-128">Parent Elements</span></span>  
  
|<span data-ttu-id="968bd-129">Element</span><span class="sxs-lookup"><span data-stu-id="968bd-129">Element</span></span>|<span data-ttu-id="968bd-130">Opis</span><span class="sxs-lookup"><span data-stu-id="968bd-130">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="968bd-131">Zawiera ustawienia wymagane przez aplikację do uczestnictwa w procesie odnajdowania usług jako klient.</span><span class="sxs-lookup"><span data-stu-id="968bd-131">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="968bd-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="968bd-132">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
