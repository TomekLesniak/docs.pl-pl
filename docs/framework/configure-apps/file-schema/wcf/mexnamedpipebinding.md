---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 64e250ae5ccb30da3f8857b94628b85b8c237a03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204713"
---
# \<mexNamedPipeBinding>

<span data-ttu-id="e0d17-101">Określa ustawienia dla powiązania używanego w wymianie wiadomości WS-MetadataExchange (WS-MEX) za pośrednictwem nazwanego potoku.</span><span class="sxs-lookup"><span data-stu-id="e0d17-101">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexNamedPipeBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="e0d17-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="e0d17-102">Syntax</span></span>  
  
```xml  
<mexNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0d17-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="e0d17-103">Attributes and Elements</span></span>  

 <span data-ttu-id="e0d17-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="e0d17-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0d17-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="e0d17-105">Attributes</span></span>  
  
|<span data-ttu-id="e0d17-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="e0d17-106">Attribute</span></span>|<span data-ttu-id="e0d17-107">Opis</span><span class="sxs-lookup"><span data-stu-id="e0d17-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="e0d17-108"><xref:System.TimeSpan>Wartość określająca interwał czasu podanego do ukończenia operacji zamknięcia.</span><span class="sxs-lookup"><span data-stu-id="e0d17-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="e0d17-109">Ta wartość powinna być większa lub równa <xref:System.TimeSpan.Zero> .</span><span class="sxs-lookup"><span data-stu-id="e0d17-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e0d17-110">Wartość domyślna to 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e0d17-110">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="e0d17-111">Ciąg zawierający nazwę konfiguracji powiązania.</span><span class="sxs-lookup"><span data-stu-id="e0d17-111">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="e0d17-112">Ta wartość powinna być unikatowa, ponieważ jest używana jako identyfikacja dla powiązania.</span><span class="sxs-lookup"><span data-stu-id="e0d17-112">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="e0d17-113">Począwszy od .NET Framework 4, powiązania i zachowania nie muszą mieć nazwy.</span><span class="sxs-lookup"><span data-stu-id="e0d17-113">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="e0d17-114">Aby uzyskać więcej informacji na temat konfiguracji domyślnej i powiązań pustego i zachowań, zobacz [Uproszczona konfiguracja](../../../wcf/simplified-configuration.md) i [Uproszczona konfiguracja dla usług WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e0d17-114">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="e0d17-115"><xref:System.TimeSpan>Wartość, która określa przedział czasu podanego na zakończenie operacji otwarcia.</span><span class="sxs-lookup"><span data-stu-id="e0d17-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="e0d17-116">Ta wartość powinna być większa lub równa <xref:System.TimeSpan.Zero> .</span><span class="sxs-lookup"><span data-stu-id="e0d17-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e0d17-117">Wartość domyślna to 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e0d17-117">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="e0d17-118">Wartość określająca <xref:System.TimeSpan> interwał czasu podanego do ukończenia operacji odbioru.</span><span class="sxs-lookup"><span data-stu-id="e0d17-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="e0d17-119">Ta wartość powinna być większa lub równa <xref:System.TimeSpan.Zero> .</span><span class="sxs-lookup"><span data-stu-id="e0d17-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e0d17-120">Wartość domyślna to 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="e0d17-120">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="e0d17-121"><xref:System.TimeSpan>Wartość określająca interwał czasu podanego do ukończenia operacji wysyłania.</span><span class="sxs-lookup"><span data-stu-id="e0d17-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="e0d17-122">Ta wartość powinna być większa lub równa <xref:System.TimeSpan.Zero> .</span><span class="sxs-lookup"><span data-stu-id="e0d17-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e0d17-123">Wartość domyślna to 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e0d17-123">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0d17-124">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="e0d17-124">Child Elements</span></span>  

 <span data-ttu-id="e0d17-125">Brak.</span><span class="sxs-lookup"><span data-stu-id="e0d17-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0d17-126">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="e0d17-126">Parent Elements</span></span>  
  
|<span data-ttu-id="e0d17-127">Element</span><span class="sxs-lookup"><span data-stu-id="e0d17-127">Element</span></span>|<span data-ttu-id="e0d17-128">Opis</span><span class="sxs-lookup"><span data-stu-id="e0d17-128">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="e0d17-129">Ten element zawiera kolekcję powiązań standardowych i niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="e0d17-129">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0d17-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e0d17-130">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="e0d17-131">Instrukcje: publikowanie metadanych dla usługi za pomocą pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="e0d17-131">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="e0d17-132">Publikowanie i pobieranie metadanych za pośrednictwem powiązania niestandardowego</span><span class="sxs-lookup"><span data-stu-id="e0d17-132">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="e0d17-133">Metadane</span><span class="sxs-lookup"><span data-stu-id="e0d17-133">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="e0d17-134">Powiązania</span><span class="sxs-lookup"><span data-stu-id="e0d17-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e0d17-135">Konfigurowanie powiązań dostarczanych przez system</span><span class="sxs-lookup"><span data-stu-id="e0d17-135">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e0d17-136">Konfigurowanie usług i klientów za pomocą wiązań</span><span class="sxs-lookup"><span data-stu-id="e0d17-136">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
