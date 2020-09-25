---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 11378e6cc8cbe8e631fd77ab74c91a616099df52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190088"
---
# \<enableWebScript>

<span data-ttu-id="e245d-101">Ten element włącza zachowanie punktu końcowego, który umożliwia korzystanie z usługi z ASP.NET AJAX stron sieci Web.</span><span class="sxs-lookup"><span data-stu-id="e245d-101">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**  
  
## <a name="syntax"></a><span data-ttu-id="e245d-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="e245d-102">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e245d-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="e245d-103">Attributes and Elements</span></span>  

 <span data-ttu-id="e245d-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="e245d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e245d-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="e245d-105">Attributes</span></span>  

 <span data-ttu-id="e245d-106">Brak.</span><span class="sxs-lookup"><span data-stu-id="e245d-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e245d-107">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="e245d-107">Child Elements</span></span>  

 <span data-ttu-id="e245d-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="e245d-108">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e245d-109">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="e245d-109">Parent Elements</span></span>  
  
|<span data-ttu-id="e245d-110">Element</span><span class="sxs-lookup"><span data-stu-id="e245d-110">Element</span></span>|<span data-ttu-id="e245d-111">Opis</span><span class="sxs-lookup"><span data-stu-id="e245d-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e245d-112">Określa zestaw zachowań punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="e245d-112">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e245d-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e245d-113">Remarks</span></span>  

 <span data-ttu-id="e245d-114">Tego zachowania należy używać tylko w połączeniu ze [\<webHttpBinding>](webhttpbinding.md) standardowym powiązaniem lub [\<webMessageEncoding>](webmessageencoding.md) elementem powiązania.</span><span class="sxs-lookup"><span data-stu-id="e245d-114">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="e245d-115">Aby uzyskać więcej informacji na temat tego zachowania, zobacz <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> .</span><span class="sxs-lookup"><span data-stu-id="e245d-115">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e245d-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e245d-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="e245d-117">Obsługa integracji AJAX i notacji JSON</span><span class="sxs-lookup"><span data-stu-id="e245d-117">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttp>](webhttp.md)
