---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 5e62201a38dc4dc251996531a4af5f294dd2395f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151106"
---
# \<clientVia>

<span data-ttu-id="bca21-101">Określa identyfikator URI, dla którego należy utworzyć kanał transportu.</span><span class="sxs-lookup"><span data-stu-id="bca21-101">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="bca21-102">Aby uzyskać więcej informacji, zobacz <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="bca21-102">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**  
  
## <a name="syntax"></a><span data-ttu-id="bca21-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="bca21-103">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bca21-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="bca21-104">Attributes and Elements</span></span>  

 <span data-ttu-id="bca21-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="bca21-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bca21-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="bca21-106">Attributes</span></span>  
  
|<span data-ttu-id="bca21-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="bca21-107">Attribute</span></span>|<span data-ttu-id="bca21-108">Opis</span><span class="sxs-lookup"><span data-stu-id="bca21-108">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="bca21-109">Ciąg określający identyfikator URI, który wskazuje trasę, którą powinien wykonać komunikat.</span><span class="sxs-lookup"><span data-stu-id="bca21-109">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bca21-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="bca21-110">Child Elements</span></span>  

 <span data-ttu-id="bca21-111">Brak</span><span class="sxs-lookup"><span data-stu-id="bca21-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bca21-112">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="bca21-112">Parent Elements</span></span>  
  
|<span data-ttu-id="bca21-113">Element</span><span class="sxs-lookup"><span data-stu-id="bca21-113">Element</span></span>|<span data-ttu-id="bca21-114">Opis</span><span class="sxs-lookup"><span data-stu-id="bca21-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="bca21-115">Określa zachowanie punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="bca21-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bca21-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bca21-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
