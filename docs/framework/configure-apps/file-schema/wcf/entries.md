---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: d3dae510ac62735138a24b8fb97a8acfffde1a98
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189971"
---
# \<entries>

<span data-ttu-id="457aa-101">Wpis routingu zawierający mapowania między filtrami routingu i docelowymi punktami końcowymi, do których mają być wysyłane komunikaty, gdy filtr jest zgodny.</span><span class="sxs-lookup"><span data-stu-id="457aa-101">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**  
  
## <a name="syntax"></a><span data-ttu-id="457aa-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="457aa-102">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="457aa-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="457aa-103">Attributes and Elements</span></span>  

 <span data-ttu-id="457aa-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="457aa-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="457aa-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="457aa-105">Attributes</span></span>  

 <span data-ttu-id="457aa-106">Brak.</span><span class="sxs-lookup"><span data-stu-id="457aa-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="457aa-107">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="457aa-107">Child Elements</span></span>  
  
|<span data-ttu-id="457aa-108">Element</span><span class="sxs-lookup"><span data-stu-id="457aa-108">Element</span></span>|<span data-ttu-id="457aa-109">Opis</span><span class="sxs-lookup"><span data-stu-id="457aa-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="457aa-110">Mapuje filtr do punktu końcowego klienta, który został wcześniej zdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="457aa-110">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="457aa-111">Komunikaty pasujące do tego filtru zostaną wysłane do tego miejsca docelowego.</span><span class="sxs-lookup"><span data-stu-id="457aa-111">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="457aa-112">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="457aa-112">Parent Elements</span></span>  
  
|<span data-ttu-id="457aa-113">Element</span><span class="sxs-lookup"><span data-stu-id="457aa-113">Element</span></span>|<span data-ttu-id="457aa-114">Opis</span><span class="sxs-lookup"><span data-stu-id="457aa-114">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="457aa-115">Sekcja konfiguracji, która zawiera tabelę routingu.</span><span class="sxs-lookup"><span data-stu-id="457aa-115">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="457aa-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="457aa-116">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
