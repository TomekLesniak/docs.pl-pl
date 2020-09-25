---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 2a994a8ba97d4c65fdaba5a85e779dd9935e3074
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195038"
---
# \<dataContractSerializer>

<span data-ttu-id="cd1ad-101">Zawiera dane konfiguracji dla programu <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="cd1ad-101">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="cd1ad-102">Ten element występuje w dwóch różnych hierarchiach.</span><span class="sxs-lookup"><span data-stu-id="cd1ad-102">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="cd1ad-103">Jeden z nich znajduje się w poniższej sekcji hierarchii schematu, a drugi jest wymieniony w sekcji uwagi.</span><span class="sxs-lookup"><span data-stu-id="cd1ad-103">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="cd1ad-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="cd1ad-104">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd1ad-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="cd1ad-105">Attributes and Elements</span></span>  

 <span data-ttu-id="cd1ad-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="cd1ad-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd1ad-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="cd1ad-107">Attributes</span></span>  
  
|<span data-ttu-id="cd1ad-108">Element</span><span class="sxs-lookup"><span data-stu-id="cd1ad-108">Element</span></span>|<span data-ttu-id="cd1ad-109">Opis</span><span class="sxs-lookup"><span data-stu-id="cd1ad-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd1ad-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="cd1ad-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="cd1ad-111">Wartość logiczna określająca, czy ignorować dane dostarczane przez punkt końcowy, gdy jest on serializowany lub deserializowany.</span><span class="sxs-lookup"><span data-stu-id="cd1ad-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="cd1ad-112">Ten atrybut jest tylko do settable dla `<dataContractSerializer>` `<behavior>` elementu.</span><span class="sxs-lookup"><span data-stu-id="cd1ad-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="cd1ad-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="cd1ad-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="cd1ad-114">Liczba całkowita, która określa maksymalną liczbę elementów do serializacji lub deserializacji.</span><span class="sxs-lookup"><span data-stu-id="cd1ad-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="cd1ad-115">Ten atrybut to 65536.</span><span class="sxs-lookup"><span data-stu-id="cd1ad-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd1ad-116">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="cd1ad-116">Child Elements</span></span>  

 <span data-ttu-id="cd1ad-117">Brak.</span><span class="sxs-lookup"><span data-stu-id="cd1ad-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd1ad-118">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="cd1ad-118">Parent Elements</span></span>  
  
|<span data-ttu-id="cd1ad-119">Element</span><span class="sxs-lookup"><span data-stu-id="cd1ad-119">Element</span></span>|<span data-ttu-id="cd1ad-120">Opis</span><span class="sxs-lookup"><span data-stu-id="cd1ad-120">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-servicebehaviors.md)|<span data-ttu-id="cd1ad-121">Kolekcja ustawień zachowania usługi.</span><span class="sxs-lookup"><span data-stu-id="cd1ad-121">A collection of settings for the behavior of a service.</span></span>|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="cd1ad-122">Reprezentuje element główny dla <xref:System.Runtime.Serialization> sekcji przestrzeni nazw i zawiera elementy dla opcji ustawień <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="cd1ad-122">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd1ad-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cd1ad-123">Remarks</span></span>  

 <span data-ttu-id="cd1ad-124">Zgodnie z wprowadzeniem tego tematu jest to druga hierarchia, w której \<X509Extension> występuje element.</span><span class="sxs-lookup"><span data-stu-id="cd1ad-124">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
  
 [\<dataContractSerializer>](datacontractserializer-element.md)  
  
 <span data-ttu-id="cd1ad-125">Aby uzyskać więcej informacji na temat znanych typów, zobacz <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="cd1ad-125">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd1ad-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cd1ad-126">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="cd1ad-127">Znane typy kontraktów danych</span><span class="sxs-lookup"><span data-stu-id="cd1ad-127">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="cd1ad-128">Transfer i serializacja danych</span><span class="sxs-lookup"><span data-stu-id="cd1ad-128">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
