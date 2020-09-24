---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: b8cb5075ba41bed5a22b152a231c7213b326a62f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153719"
---
# \<services>

<span data-ttu-id="092df-101">Usługi są zdefiniowane w `services` sekcji pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="092df-101">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="092df-102">Każda usługa ma swoją własną `service` sekcję konfiguracyjną.</span><span class="sxs-lookup"><span data-stu-id="092df-102">Each service has its own `service` configuration section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**  
  
## <a name="syntax"></a><span data-ttu-id="092df-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="092df-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="092df-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="092df-104">Attributes and Elements</span></span>  

 <span data-ttu-id="092df-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="092df-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="092df-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="092df-106">Attributes</span></span>  

 <span data-ttu-id="092df-107">Brak</span><span class="sxs-lookup"><span data-stu-id="092df-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="092df-108">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="092df-108">Child Elements</span></span>  
  
|<span data-ttu-id="092df-109">Element</span><span class="sxs-lookup"><span data-stu-id="092df-109">Element</span></span>|<span data-ttu-id="092df-110">Opis</span><span class="sxs-lookup"><span data-stu-id="092df-110">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="092df-111">Zdefiniuj kontrakt usługi, zachowanie i punkty końcowe określonej usługi.</span><span class="sxs-lookup"><span data-stu-id="092df-111">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="092df-112">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="092df-112">Parent Elements</span></span>  
  
|<span data-ttu-id="092df-113">Element</span><span class="sxs-lookup"><span data-stu-id="092df-113">Element</span></span>|<span data-ttu-id="092df-114">Opis</span><span class="sxs-lookup"><span data-stu-id="092df-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="092df-115">Element główny wszystkich elementów konfiguracji Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="092df-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="092df-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="092df-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
