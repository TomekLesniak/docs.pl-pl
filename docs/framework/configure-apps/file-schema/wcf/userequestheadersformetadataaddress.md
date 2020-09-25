---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: a323e6da0eb173e303d70cc3b7309b898a805573
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172817"
---
# \<useRequestHeadersForMetadataAddress>

<span data-ttu-id="b1cab-101">Umożliwia pobieranie informacji o adresie metadanych z nagłówków komunikatów żądania.</span><span class="sxs-lookup"><span data-stu-id="b1cab-101">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**  
  
## <a name="syntax"></a><span data-ttu-id="b1cab-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="b1cab-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1cab-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="b1cab-103">Attributes and Elements</span></span>  

 <span data-ttu-id="b1cab-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="b1cab-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1cab-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="b1cab-105">Attributes</span></span>  

 <span data-ttu-id="b1cab-106">Brak.</span><span class="sxs-lookup"><span data-stu-id="b1cab-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b1cab-107">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="b1cab-107">Child Elements</span></span>  
  
|<span data-ttu-id="b1cab-108">Element</span><span class="sxs-lookup"><span data-stu-id="b1cab-108">Element</span></span>|<span data-ttu-id="b1cab-109">Opis</span><span class="sxs-lookup"><span data-stu-id="b1cab-109">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="b1cab-110">Kolekcja portów domyślnych wyświetla domyślne punkty końcowe komunikacji, do których nasłuchuje aplikacja kliencka.</span><span class="sxs-lookup"><span data-stu-id="b1cab-110">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b1cab-111">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="b1cab-111">Parent Elements</span></span>  
  
|<span data-ttu-id="b1cab-112">Element</span><span class="sxs-lookup"><span data-stu-id="b1cab-112">Element</span></span>|<span data-ttu-id="b1cab-113">Opis</span><span class="sxs-lookup"><span data-stu-id="b1cab-113">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b1cab-114">Określa zachowanie elementu.</span><span class="sxs-lookup"><span data-stu-id="b1cab-114">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1cab-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b1cab-115">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
