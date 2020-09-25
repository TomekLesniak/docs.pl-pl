---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 0d12f886eaee6283ee686209dfc129e397a8e1fe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204700"
---
# \<mexTcpBinding>

<span data-ttu-id="06a1c-101">Określa ustawienia dla powiązania używanego w wymianie wiadomości WS-MetadataExchange (WS-MEX) za pośrednictwem protokołu TCP.</span><span class="sxs-lookup"><span data-stu-id="06a1c-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="06a1c-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="06a1c-102">Syntax</span></span>  
  
```xml  
<mexTcpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06a1c-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="06a1c-103">Attributes and Elements</span></span>  

 <span data-ttu-id="06a1c-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="06a1c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06a1c-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="06a1c-105">Attributes</span></span>  
  
|<span data-ttu-id="06a1c-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="06a1c-106">Attribute</span></span>|<span data-ttu-id="06a1c-107">Opis</span><span class="sxs-lookup"><span data-stu-id="06a1c-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="06a1c-108"><xref:System.TimeSpan>Wartość określająca interwał czasu podanego do ukończenia operacji zamknięcia.</span><span class="sxs-lookup"><span data-stu-id="06a1c-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="06a1c-109">Ta wartość powinna być większa lub równa <xref:System.TimeSpan.Zero> .</span><span class="sxs-lookup"><span data-stu-id="06a1c-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="06a1c-110">Wartość domyślna to 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="06a1c-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="06a1c-111">Ciąg zawierający nazwę konfiguracji powiązania.</span><span class="sxs-lookup"><span data-stu-id="06a1c-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="06a1c-112">Ta wartość powinna być unikatowa, ponieważ jest używana jako identyfikacja dla powiązania.</span><span class="sxs-lookup"><span data-stu-id="06a1c-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="06a1c-113">Począwszy od .NET Framework 4, powiązania i zachowania nie muszą mieć nazwy.</span><span class="sxs-lookup"><span data-stu-id="06a1c-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="06a1c-114">Aby uzyskać więcej informacji na temat konfiguracji domyślnej i powiązań pustego i zachowań, zobacz [Uproszczona konfiguracja](../../../wcf/simplified-configuration.md) i [Uproszczona konfiguracja dla usług WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="06a1c-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="06a1c-115"><xref:System.TimeSpan>Wartość, która określa przedział czasu podanego na zakończenie operacji otwarcia.</span><span class="sxs-lookup"><span data-stu-id="06a1c-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="06a1c-116">Ta wartość powinna być większa lub równa <xref:System.TimeSpan.Zero> .</span><span class="sxs-lookup"><span data-stu-id="06a1c-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="06a1c-117">Wartość domyślna to 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="06a1c-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="06a1c-118">Wartość określająca <xref:System.TimeSpan> interwał czasu podanego do ukończenia operacji odbioru.</span><span class="sxs-lookup"><span data-stu-id="06a1c-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="06a1c-119">Ta wartość powinna być większa lub równa <xref:System.TimeSpan.Zero> .</span><span class="sxs-lookup"><span data-stu-id="06a1c-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="06a1c-120">Wartość domyślna to 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="06a1c-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="06a1c-121"><xref:System.TimeSpan>Wartość określająca interwał czasu podanego do ukończenia operacji wysyłania.</span><span class="sxs-lookup"><span data-stu-id="06a1c-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="06a1c-122">Ta wartość powinna być większa lub równa <xref:System.TimeSpan.Zero> .</span><span class="sxs-lookup"><span data-stu-id="06a1c-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="06a1c-123">Wartość domyślna to 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="06a1c-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06a1c-124">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="06a1c-124">Child Elements</span></span>  

 <span data-ttu-id="06a1c-125">Brak.</span><span class="sxs-lookup"><span data-stu-id="06a1c-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06a1c-126">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="06a1c-126">Parent Elements</span></span>  
  
|<span data-ttu-id="06a1c-127">Element</span><span class="sxs-lookup"><span data-stu-id="06a1c-127">Element</span></span>|<span data-ttu-id="06a1c-128">Opis</span><span class="sxs-lookup"><span data-stu-id="06a1c-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="06a1c-129">Ten element zawiera kolekcję powiązań standardowych i niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="06a1c-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06a1c-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="06a1c-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="06a1c-131">Instrukcje: publikowanie metadanych dla usługi za pomocą pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="06a1c-131">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="06a1c-132">Publikowanie i pobieranie metadanych za pośrednictwem powiązania niestandardowego</span><span class="sxs-lookup"><span data-stu-id="06a1c-132">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="06a1c-133">Metadane</span><span class="sxs-lookup"><span data-stu-id="06a1c-133">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="06a1c-134">Powiązania</span><span class="sxs-lookup"><span data-stu-id="06a1c-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="06a1c-135">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="06a1c-135">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="06a1c-136">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="06a1c-136">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
