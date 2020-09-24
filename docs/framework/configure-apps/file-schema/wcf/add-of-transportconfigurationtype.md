---
title: <add> dla <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: 9bef44ed39ee892080342058206f779b38fb460d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151158"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="ec788-102">\<add> dla \<transportConfigurationType></span><span class="sxs-lookup"><span data-stu-id="ec788-102">\<add> of \<transportConfigurationType></span></span>

<span data-ttu-id="ec788-103">Ten element jest parą klucz/wartość, która identyfikuje typ określonego transportu.</span><span class="sxs-lookup"><span data-stu-id="ec788-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="ec788-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="ec788-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec788-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="ec788-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ec788-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="ec788-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec788-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="ec788-107">Attributes</span></span>  
  
|<span data-ttu-id="ec788-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="ec788-108">Attribute</span></span>|<span data-ttu-id="ec788-109">Opis</span><span class="sxs-lookup"><span data-stu-id="ec788-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ec788-110">name</span><span class="sxs-lookup"><span data-stu-id="ec788-110">name</span></span>|<span data-ttu-id="ec788-111">Wymagany atrybut ciągu.</span><span class="sxs-lookup"><span data-stu-id="ec788-111">Required String attribute.</span></span><br /><br /> <span data-ttu-id="ec788-112">Zawiera klucz zdefiniowany przez użytkownika, który jednoznacznie identyfikuje typ transportu.</span><span class="sxs-lookup"><span data-stu-id="ec788-112">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="ec788-113">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="ec788-113">transportConfigurationType</span></span>|<span data-ttu-id="ec788-114">Ciąg, który zawiera typ implementujący określony transport.</span><span class="sxs-lookup"><span data-stu-id="ec788-114">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec788-115">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="ec788-115">Child Elements</span></span>  

 <span data-ttu-id="ec788-116">Brak</span><span class="sxs-lookup"><span data-stu-id="ec788-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec788-117">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="ec788-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ec788-118">Element</span><span class="sxs-lookup"><span data-stu-id="ec788-118">Element</span></span>|<span data-ttu-id="ec788-119">Opis</span><span class="sxs-lookup"><span data-stu-id="ec788-119">Description</span></span>|  
|-------------|-----------------|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|<span data-ttu-id="ec788-120">Kolekcja typów, które implementują określony transport.</span><span class="sxs-lookup"><span data-stu-id="ec788-120">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ec788-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="ec788-121">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="ec788-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ec788-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="ec788-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="ec788-123">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
