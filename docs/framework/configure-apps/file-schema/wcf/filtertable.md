---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: fb36feedc5fb2cbdf3827cbe44242c7ac6ab8a9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185694"
---
# \<filterTable>

<span data-ttu-id="34e90-101">Reprezentuje tabelę routingu zawierającą listę filtrów służących do szacowania komunikatów oraz punkt końcowy klienta, do którego mają być kierowane komunikaty, jeśli filtr ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="34e90-101">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**  
  
## <a name="syntax"></a><span data-ttu-id="34e90-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="34e90-102">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
     name="String">
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34e90-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="34e90-103">Attributes and Elements</span></span>  

 <span data-ttu-id="34e90-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="34e90-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34e90-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="34e90-105">Attributes</span></span>  
  
|<span data-ttu-id="34e90-106">Element</span><span class="sxs-lookup"><span data-stu-id="34e90-106">Element</span></span>|<span data-ttu-id="34e90-107">Opis</span><span class="sxs-lookup"><span data-stu-id="34e90-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34e90-108">name</span><span class="sxs-lookup"><span data-stu-id="34e90-108">name</span></span>|<span data-ttu-id="34e90-109">Ciąg zawierający unikatową nazwę tego elementu konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="34e90-109">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34e90-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="34e90-110">Child Elements</span></span>  
  
|<span data-ttu-id="34e90-111">Element</span><span class="sxs-lookup"><span data-stu-id="34e90-111">Element</span></span>|<span data-ttu-id="34e90-112">Opis</span><span class="sxs-lookup"><span data-stu-id="34e90-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="34e90-113">Mapowania między filtrami routingu i docelowymi punktami końcowymi do wysyłania komunikatów, gdy filtr jest zgodny.</span><span class="sxs-lookup"><span data-stu-id="34e90-113">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="34e90-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="34e90-114">Parent Elements</span></span>  
  
|<span data-ttu-id="34e90-115">Element</span><span class="sxs-lookup"><span data-stu-id="34e90-115">Element</span></span>|<span data-ttu-id="34e90-116">Opis</span><span class="sxs-lookup"><span data-stu-id="34e90-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="34e90-117">Sekcja konfiguracji, która zawiera tabele routingu.</span><span class="sxs-lookup"><span data-stu-id="34e90-117">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34e90-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="34e90-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
