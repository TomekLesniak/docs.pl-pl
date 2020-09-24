---
title: <add> dla <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 156d8b8d9d0eb05efbf306434ab4555a98bc317e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149052"
---
# <a name="add-of-entries"></a><span data-ttu-id="d6ee6-102">\<add> dla \<entries></span><span class="sxs-lookup"><span data-stu-id="d6ee6-102">\<add> of \<entries></span></span>

<span data-ttu-id="d6ee6-103">Reprezentuje wpis routingu, który mapuje filtr do punktu końcowego klienta, który został wcześniej zdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="d6ee6-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="d6ee6-104">Komunikaty pasujące do tego filtru zostaną wysłane do tego miejsca docelowego.</span><span class="sxs-lookup"><span data-stu-id="d6ee6-104">Messages matching this filter will be sent to this destination.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="d6ee6-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="d6ee6-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6ee6-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="d6ee6-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d6ee6-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="d6ee6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6ee6-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="d6ee6-108">Attributes</span></span>  
  
|<span data-ttu-id="d6ee6-109">Atrybut</span><span class="sxs-lookup"><span data-stu-id="d6ee6-109">Attribute</span></span>|<span data-ttu-id="d6ee6-110">Opis</span><span class="sxs-lookup"><span data-stu-id="d6ee6-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d6ee6-111">backupList</span><span class="sxs-lookup"><span data-stu-id="d6ee6-111">backupList</span></span>|<span data-ttu-id="d6ee6-112">Ciąg określający odwołanie do listy kopii zapasowych punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="d6ee6-112">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="d6ee6-113">endpoint</span><span class="sxs-lookup"><span data-stu-id="d6ee6-113">endpoint</span></span>|<span data-ttu-id="d6ee6-114">Ciąg określający odwołanie do punktu końcowego klienta, który będzie odbierać komunikaty zgodne z filtrem określonym przez `filterName` atrybut.</span><span class="sxs-lookup"><span data-stu-id="d6ee6-114">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="d6ee6-115">filterName</span><span class="sxs-lookup"><span data-stu-id="d6ee6-115">filterName</span></span>|<span data-ttu-id="d6ee6-116">Ciąg określający odwołanie do elementu filtru.</span><span class="sxs-lookup"><span data-stu-id="d6ee6-116">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="d6ee6-117">priority</span><span class="sxs-lookup"><span data-stu-id="d6ee6-117">priority</span></span>|<span data-ttu-id="d6ee6-118">Liczba całkowita, która określa priorytet tego wpisu.</span><span class="sxs-lookup"><span data-stu-id="d6ee6-118">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="d6ee6-119">Wpisy w tabeli routingu będą oceniane na podstawie priorytetu, a wartość 0 to najniższy priorytet.</span><span class="sxs-lookup"><span data-stu-id="d6ee6-119">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="d6ee6-120">Wszystkie wpisy o określonym priorytecie są oceniane jednocześnie, jeśli nie zostanie znaleziony pasujący wpis dla bieżącego priorytetu, zostanie obliczony następny poziom priorytetu.</span><span class="sxs-lookup"><span data-stu-id="d6ee6-120">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="d6ee6-121">Ta wartość jest opcjonalna.</span><span class="sxs-lookup"><span data-stu-id="d6ee6-121">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6ee6-122">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="d6ee6-122">Child Elements</span></span>  

 <span data-ttu-id="d6ee6-123">Brak.</span><span class="sxs-lookup"><span data-stu-id="d6ee6-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6ee6-124">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="d6ee6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d6ee6-125">Element</span><span class="sxs-lookup"><span data-stu-id="d6ee6-125">Element</span></span>|<span data-ttu-id="d6ee6-126">Opis</span><span class="sxs-lookup"><span data-stu-id="d6ee6-126">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="d6ee6-127">Sekcja konfiguracji, która zawiera wpisy mapowania routingu.</span><span class="sxs-lookup"><span data-stu-id="d6ee6-127">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6ee6-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d6ee6-128">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
