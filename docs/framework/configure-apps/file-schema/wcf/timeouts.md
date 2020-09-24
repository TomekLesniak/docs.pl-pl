---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: f7e513bb5c486fa5f7c39c9b2e3cfcd26bd7c219
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157099"
---
# \<timeOuts>

<span data-ttu-id="44513-101">Reprezentuje element konfiguracji, który określa przedział czasu dozwolony na otwarcie lub zamknięcie hosta usługi.</span><span class="sxs-lookup"><span data-stu-id="44513-101">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="44513-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="44513-102">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44513-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="44513-103">Attributes and Elements</span></span>  

 <span data-ttu-id="44513-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="44513-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44513-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="44513-105">Attributes</span></span>  
  
|<span data-ttu-id="44513-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="44513-106">Attribute</span></span>|<span data-ttu-id="44513-107">Opis</span><span class="sxs-lookup"><span data-stu-id="44513-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="44513-108"><xref:System.TimeSpan>Wartość, która określa przedział czasu, jaki może być zamknięty dla hosta usługi.</span><span class="sxs-lookup"><span data-stu-id="44513-108">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="44513-109"><xref:System.TimeSpan>Wartość, która określa przedział czasu, jaki może otworzyć Host usługi.</span><span class="sxs-lookup"><span data-stu-id="44513-109">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44513-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="44513-110">Child Elements</span></span>  

 <span data-ttu-id="44513-111">Brak.</span><span class="sxs-lookup"><span data-stu-id="44513-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44513-112">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="44513-112">Parent Elements</span></span>  
  
|<span data-ttu-id="44513-113">Element</span><span class="sxs-lookup"><span data-stu-id="44513-113">Element</span></span>|<span data-ttu-id="44513-114">Opis</span><span class="sxs-lookup"><span data-stu-id="44513-114">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="44513-115">Element konfiguracji, który określa ustawienia dla hosta usługi.</span><span class="sxs-lookup"><span data-stu-id="44513-115">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44513-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="44513-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="44513-117">Hosting</span><span class="sxs-lookup"><span data-stu-id="44513-117">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
