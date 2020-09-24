---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 92d3de42daf6f7baf288e3e74242381a60e76618
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153602"
---
# \<serviceTimeouts>

<span data-ttu-id="843db-101">Określa limit czasu dla usługi.</span><span class="sxs-lookup"><span data-stu-id="843db-101">Specifies the timeout for a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**  
  
## <a name="syntax"></a><span data-ttu-id="843db-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="843db-102">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="843db-103">Typ</span><span class="sxs-lookup"><span data-stu-id="843db-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="843db-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="843db-104">Attributes and Elements</span></span>  

 <span data-ttu-id="843db-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="843db-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="843db-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="843db-106">Attributes</span></span>  
  
|<span data-ttu-id="843db-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="843db-107">Attribute</span></span>|<span data-ttu-id="843db-108">Opis</span><span class="sxs-lookup"><span data-stu-id="843db-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="843db-109"><xref:System.TimeSpan>Wartość, która określa przedział czasu, przez który transakcja musi przepływać z klienta do serwera.</span><span class="sxs-lookup"><span data-stu-id="843db-109">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="843db-110">Wartość domyślna to "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="843db-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="843db-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="843db-111">Child Elements</span></span>  

 <span data-ttu-id="843db-112">Brak.</span><span class="sxs-lookup"><span data-stu-id="843db-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="843db-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="843db-113">Parent Elements</span></span>  
  
|<span data-ttu-id="843db-114">Element</span><span class="sxs-lookup"><span data-stu-id="843db-114">Element</span></span>|<span data-ttu-id="843db-115">Opis</span><span class="sxs-lookup"><span data-stu-id="843db-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="843db-116">Określa zachowanie elementu.</span><span class="sxs-lookup"><span data-stu-id="843db-116">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="843db-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="843db-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
