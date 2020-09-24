---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 5e772e23b21c566c906be854e33b924698dcf3e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158711"
---
# \<privacyNoticeAt>

<span data-ttu-id="d6e47-101">Reprezentuje element konfiguracji, który określa powiadomienie o prywatności użyte w `wsFederationHttp` powiązaniu.</span><span class="sxs-lookup"><span data-stu-id="d6e47-101">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**  
  
## <a name="syntax"></a><span data-ttu-id="d6e47-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="d6e47-102">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="d6e47-103">Typ</span><span class="sxs-lookup"><span data-stu-id="d6e47-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6e47-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="d6e47-104">Attributes and Elements</span></span>  

 <span data-ttu-id="d6e47-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="d6e47-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6e47-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="d6e47-106">Attributes</span></span>  
  
|<span data-ttu-id="d6e47-107">Atrybut</span><span class="sxs-lookup"><span data-stu-id="d6e47-107">Attribute</span></span>|<span data-ttu-id="d6e47-108">Opis</span><span class="sxs-lookup"><span data-stu-id="d6e47-108">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="d6e47-109">Ciąg określający identyfikator URI, w którym znajduje się powiadomienie o prywatności.</span><span class="sxs-lookup"><span data-stu-id="d6e47-109">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="d6e47-110">Liczba całkowita określająca wersję tego powiadomienia o ochronie prywatności.</span><span class="sxs-lookup"><span data-stu-id="d6e47-110">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6e47-111">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="d6e47-111">Child Elements</span></span>  

 <span data-ttu-id="d6e47-112">Brak.</span><span class="sxs-lookup"><span data-stu-id="d6e47-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6e47-113">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="d6e47-113">Parent Elements</span></span>  
  
|<span data-ttu-id="d6e47-114">Element</span><span class="sxs-lookup"><span data-stu-id="d6e47-114">Element</span></span>|<span data-ttu-id="d6e47-115">Opis</span><span class="sxs-lookup"><span data-stu-id="d6e47-115">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="d6e47-116">Definiuje wszystkie możliwości powiązań niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="d6e47-116">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6e47-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d6e47-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d6e47-118">Powiązania</span><span class="sxs-lookup"><span data-stu-id="d6e47-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d6e47-119">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="d6e47-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d6e47-120">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="d6e47-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
