---
title: <workflowInstanceManagement>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
ms.openlocfilehash: 532d4c31a582b2b0cd90f6f42b20e00790f9ab02
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148662"
---
# \<workflowInstanceManagement>

<span data-ttu-id="78742-101">Zachowanie usługi, które umożliwia określenie ustawień, które kontrolują, jak są uruchamiane wystąpienia przepływu pracy, łącznie z trwałości, nieobsługiwanych wyjątków zachowanie i zachowanie bezczynności.</span><span class="sxs-lookup"><span data-stu-id="78742-101">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceManagement>**  
  
## <a name="syntax"></a><span data-ttu-id="78742-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="78742-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowInstanceManagement authorizedWindowsGroup="" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78742-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="78742-103">Attributes and Elements</span></span>  

 <span data-ttu-id="78742-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="78742-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78742-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="78742-105">Attributes</span></span>  
  
|<span data-ttu-id="78742-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="78742-106">Attribute</span></span>|<span data-ttu-id="78742-107">Opis</span><span class="sxs-lookup"><span data-stu-id="78742-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78742-108">authorizedWindowsGroup</span><span class="sxs-lookup"><span data-stu-id="78742-108">authorizedWindowsGroup</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="78742-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="78742-109">Child Elements</span></span>  

 <span data-ttu-id="78742-110">Brak.</span><span class="sxs-lookup"><span data-stu-id="78742-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78742-111">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="78742-111">Parent Elements</span></span>  
  
|<span data-ttu-id="78742-112">Element</span><span class="sxs-lookup"><span data-stu-id="78742-112">Element</span></span>|<span data-ttu-id="78742-113">Opis</span><span class="sxs-lookup"><span data-stu-id="78742-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78742-114">\<behavior> z \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="78742-114">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="78742-115">Określa zachowanie elementu.</span><span class="sxs-lookup"><span data-stu-id="78742-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78742-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="78742-116">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>
