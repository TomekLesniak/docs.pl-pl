---
title: <extensions> Paragraf
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: f3eb5d446291dfa6b7c8e0f1ee2b6a5cf53c2162
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185785"
---
# <a name="extensions-section"></a><span data-ttu-id="fc062-102">\<extensions> Paragraf</span><span class="sxs-lookup"><span data-stu-id="fc062-102">\<extensions> section</span></span>

<span data-ttu-id="fc062-103">Ta sekcja konfiguracji zawiera kolekcję rozszerzeń, które umożliwiają użytkownikowi tworzenie powiązań zdefiniowanych przez użytkownika, zachowań i innych aspektów rozszerzeń.</span><span class="sxs-lookup"><span data-stu-id="fc062-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**  
  
## <a name="syntax"></a><span data-ttu-id="fc062-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="fc062-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
    </bindingExtensions>
    <behaviorExtensions>
    </behaviorExtensions>
    <bindingElementExtensions>
    </bindingElementExtensions>
    <endpointExtensions>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc062-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="fc062-105">Attributes and Elements</span></span>  

 <span data-ttu-id="fc062-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="fc062-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc062-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="fc062-107">Attributes</span></span>  

 <span data-ttu-id="fc062-108">Brak.</span><span class="sxs-lookup"><span data-stu-id="fc062-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fc062-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="fc062-109">Child Elements</span></span>  
  
|<span data-ttu-id="fc062-110">Element</span><span class="sxs-lookup"><span data-stu-id="fc062-110">Element</span></span>|<span data-ttu-id="fc062-111">Opis</span><span class="sxs-lookup"><span data-stu-id="fc062-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviorExtensions>](behaviorextensions.md)|<span data-ttu-id="fc062-112">Ta sekcja zawiera elementy podrzędne, które określają rozszerzenia zachowań, które umożliwiają użytkownikowi dostosowanie zachowań usługi lub punktów końcowych.</span><span class="sxs-lookup"><span data-stu-id="fc062-112">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[\<bindingElementExtensions>](bindingelementextensions.md)|<span data-ttu-id="fc062-113">Ta sekcja umożliwia korzystanie z niestandardowego elementu powiązania z pliku konfiguracji komputera lub aplikacji.</span><span class="sxs-lookup"><span data-stu-id="fc062-113">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[\<bindingExtensions>](bindingextensions.md)|<span data-ttu-id="fc062-114">Ta sekcja zawiera elementy podrzędne, które określają rozszerzenia powiązań, które umożliwiają użytkownikowi dostosowanie powiązań.</span><span class="sxs-lookup"><span data-stu-id="fc062-114">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[\<endpointExtensions>](endpointextensions.md)|<span data-ttu-id="fc062-115">Ta sekcja zawiera elementy podrzędne, które rejestrują standardowe punkty końcowe.</span><span class="sxs-lookup"><span data-stu-id="fc062-115">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fc062-116">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="fc062-116">Parent Elements</span></span>  
  
|<span data-ttu-id="fc062-117">Element</span><span class="sxs-lookup"><span data-stu-id="fc062-117">Element</span></span>|<span data-ttu-id="fc062-118">Opis</span><span class="sxs-lookup"><span data-stu-id="fc062-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc062-119">System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fc062-119">system.ServiceModel</span></span>|<span data-ttu-id="fc062-120">Element główny wszystkich elementów konfiguracji WCF.</span><span class="sxs-lookup"><span data-stu-id="fc062-120">The root element of all WCF configuration elements.</span></span>|
