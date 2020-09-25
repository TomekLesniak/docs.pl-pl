---
title: <behaviors> przepływu pracy
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: 21974f77526f55a47c014a285efd3bbac6fc1f7b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189607"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="90a94-102">\<behaviors> przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="90a94-102">\<behaviors> of workflow</span></span>

<span data-ttu-id="90a94-103">Ten element zawiera kolekcję **serviceBehaviors** .</span><span class="sxs-lookup"><span data-stu-id="90a94-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="90a94-104">Każdy element w kolekcji definiuje zachowanie elementy używane przez usługi przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="90a94-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="90a94-105">Każdy element zachowania jest identyfikowany przez jego unikatowy atrybut **nazwy** .</span><span class="sxs-lookup"><span data-stu-id="90a94-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="90a94-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="90a94-106">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90a94-107">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="90a94-107">Attributes and Elements</span></span>  

 <span data-ttu-id="90a94-108">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="90a94-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90a94-109">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="90a94-109">Attributes</span></span>  

 <span data-ttu-id="90a94-110">Brak</span><span class="sxs-lookup"><span data-stu-id="90a94-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="90a94-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="90a94-111">Child Elements</span></span>  
  
|<span data-ttu-id="90a94-112">Element</span><span class="sxs-lookup"><span data-stu-id="90a94-112">Element</span></span>|<span data-ttu-id="90a94-113">Opis</span><span class="sxs-lookup"><span data-stu-id="90a94-113">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="90a94-114">Ta sekcja konfiguracji reprezentuje wszystkie zachowania zdefiniowanych na potrzeby usługi określonego przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="90a94-114">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="90a94-115">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="90a94-115">Parent Elements</span></span>  
  
|<span data-ttu-id="90a94-116">Element</span><span class="sxs-lookup"><span data-stu-id="90a94-116">Element</span></span>|<span data-ttu-id="90a94-117">Opis</span><span class="sxs-lookup"><span data-stu-id="90a94-117">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](../wcf/system-servicemodel.md)|<span data-ttu-id="90a94-118">Element główny wszystkich elementów konfiguracji przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="90a94-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90a94-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="90a94-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="90a94-120">Konfigurowanie i rozszerzanie środowiska uruchomieniowego za pomocą zachowań</span><span class="sxs-lookup"><span data-stu-id="90a94-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
