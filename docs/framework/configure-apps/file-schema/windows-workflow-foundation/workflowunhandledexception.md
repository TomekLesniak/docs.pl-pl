---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 6e3993e43aac746f380a30341fe4ebffcd257c5f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148519"
---
# \<workflowUnhandledException>

<span data-ttu-id="4ecc4-101">Zachowanie usługi, który umożliwia określenie Akcja podejmowana po wystąpieniu nieobsługiwanego wyjątku w ramach usługi przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="4ecc4-101">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowUnhandledException>**  
  
## <a name="syntax"></a><span data-ttu-id="4ecc4-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="4ecc4-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ecc4-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="4ecc4-103">Attributes and Elements</span></span>  

 <span data-ttu-id="4ecc4-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="4ecc4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ecc4-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="4ecc4-105">Attributes</span></span>  
  
|<span data-ttu-id="4ecc4-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="4ecc4-106">Attribute</span></span>|<span data-ttu-id="4ecc4-107">Opis</span><span class="sxs-lookup"><span data-stu-id="4ecc4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ecc4-108">akcja</span><span class="sxs-lookup"><span data-stu-id="4ecc4-108">action</span></span>|<span data-ttu-id="4ecc4-109">Ciąg, który określa akcję, która ma zostać podjęta po wystąpieniu nieobsługiwanego wyjątku.</span><span class="sxs-lookup"><span data-stu-id="4ecc4-109">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="4ecc4-110">Ten atrybut nie ma typu<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span><span class="sxs-lookup"><span data-stu-id="4ecc4-110">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ecc4-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="4ecc4-111">Child Elements</span></span>  

 <span data-ttu-id="4ecc4-112">Brak.</span><span class="sxs-lookup"><span data-stu-id="4ecc4-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ecc4-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="4ecc4-113">Parent Elements</span></span>  
  
|<span data-ttu-id="4ecc4-114">Element</span><span class="sxs-lookup"><span data-stu-id="4ecc4-114">Element</span></span>|<span data-ttu-id="4ecc4-115">Opis</span><span class="sxs-lookup"><span data-stu-id="4ecc4-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ecc4-116">\<behavior> z \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4ecc4-116">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="4ecc4-117">Określa zachowanie elementu.</span><span class="sxs-lookup"><span data-stu-id="4ecc4-117">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ecc4-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4ecc4-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
