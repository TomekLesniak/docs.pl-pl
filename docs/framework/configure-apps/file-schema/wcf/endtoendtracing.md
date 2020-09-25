---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 6b50c0c3db644787fe41ee58ced7eb640e7295f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190023"
---
# \<endToEndTracing>

<span data-ttu-id="cee81-101">Element konfiguracji, który pozwala na włączenie i wyłączenie różnych aspektów śledzenia end-to-end podczas uruchamiania aplikacji usługi.</span><span class="sxs-lookup"><span data-stu-id="cee81-101">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**  
  
## <a name="syntax"></a><span data-ttu-id="cee81-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="cee81-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cee81-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="cee81-103">Attributes and Elements</span></span>  

 <span data-ttu-id="cee81-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="cee81-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cee81-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="cee81-105">Attributes</span></span>  
  
|<span data-ttu-id="cee81-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="cee81-106">Attribute</span></span>|<span data-ttu-id="cee81-107">Opis</span><span class="sxs-lookup"><span data-stu-id="cee81-107">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="cee81-108">Wartość logiczna określająca, czy włączone jest śledzenie aktywności.</span><span class="sxs-lookup"><span data-stu-id="cee81-108">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="cee81-109">Wartość logiczna określająca, czy włączone jest śledzenie przepływu wiadomości.</span><span class="sxs-lookup"><span data-stu-id="cee81-109">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="cee81-110">Wartość logiczna określająca, czy propagowany atrybut jest ustawiony na wartość true.</span><span class="sxs-lookup"><span data-stu-id="cee81-110">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cee81-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="cee81-111">Child Elements</span></span>  

 <span data-ttu-id="cee81-112">Brak.</span><span class="sxs-lookup"><span data-stu-id="cee81-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cee81-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="cee81-113">Parent Elements</span></span>  
  
|<span data-ttu-id="cee81-114">Element</span><span class="sxs-lookup"><span data-stu-id="cee81-114">Element</span></span>|<span data-ttu-id="cee81-115">Opis</span><span class="sxs-lookup"><span data-stu-id="cee81-115">Description</span></span>|  
|-------------|-----------------|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="cee81-116">Definiuje ustawienia WCF na potrzeby inspekcji i kontroli środowiska uruchomieniowego dla administratora.</span><span class="sxs-lookup"><span data-stu-id="cee81-116">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cee81-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cee81-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="cee81-118">Kompleksowe śledzenie</span><span class="sxs-lookup"><span data-stu-id="cee81-118">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
