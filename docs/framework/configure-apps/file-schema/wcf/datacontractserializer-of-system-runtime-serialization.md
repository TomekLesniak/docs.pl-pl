---
title: <dataContractSerializer> <system. Runtime. Serialization>
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: a8d379e7a37bca0cdb58836a6afdf814320e2411
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190192"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a><span data-ttu-id="c7f34-102">\<dataContractSerializer> dla \<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="c7f34-102">\<dataContractSerializer> of \<system.runtime.serialization></span></span>

<span data-ttu-id="c7f34-103">Zawiera dane konfiguracji dla programu <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="c7f34-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a><span data-ttu-id="c7f34-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c7f34-104">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer"
                       type="String" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7f34-105">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="c7f34-105">Attributes and Elements</span></span>  

 <span data-ttu-id="c7f34-106">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="c7f34-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7f34-107">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="c7f34-107">Attributes</span></span>  
  
|<span data-ttu-id="c7f34-108">Element</span><span class="sxs-lookup"><span data-stu-id="c7f34-108">Element</span></span>|<span data-ttu-id="c7f34-109">Opis</span><span class="sxs-lookup"><span data-stu-id="c7f34-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7f34-110">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="c7f34-110">ignoreExtensionDataObject</span></span>|<span data-ttu-id="c7f34-111">Wartość logiczna określająca, czy ignorować dane dostarczane przez punkt końcowy, gdy jest on serializowany lub deserializowany.</span><span class="sxs-lookup"><span data-stu-id="c7f34-111">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="c7f34-112">Ten atrybut jest tylko do settable dla `<dataContractSerializer>` `<behavior>` elementu.</span><span class="sxs-lookup"><span data-stu-id="c7f34-112">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="c7f34-113">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="c7f34-113">maxItemsInObjectGraph</span></span>|<span data-ttu-id="c7f34-114">Liczba całkowita, która określa maksymalną liczbę elementów do serializacji lub deserializacji.</span><span class="sxs-lookup"><span data-stu-id="c7f34-114">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="c7f34-115">Ten atrybut to 65536.</span><span class="sxs-lookup"><span data-stu-id="c7f34-115">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7f34-116">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="c7f34-116">Child Elements</span></span>  
  
|<span data-ttu-id="c7f34-117">Element</span><span class="sxs-lookup"><span data-stu-id="c7f34-117">Element</span></span>|<span data-ttu-id="c7f34-118">Opis</span><span class="sxs-lookup"><span data-stu-id="c7f34-118">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="c7f34-119">Zawiera znane typy <xref:System.Runtime.Serialization.DataContractSerializer> używane podczas deserializacji.</span><span class="sxs-lookup"><span data-stu-id="c7f34-119">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span><br /><br /> <span data-ttu-id="c7f34-120">Aby uzyskać więcej informacji na temat kontraktów danych i znanych typów, zobacz [znane typy kontraktu danych](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="c7f34-120">For more information about data contracts and known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c7f34-121">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="c7f34-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c7f34-122">Element</span><span class="sxs-lookup"><span data-stu-id="c7f34-122">Element</span></span>|<span data-ttu-id="c7f34-123">Opis</span><span class="sxs-lookup"><span data-stu-id="c7f34-123">Description</span></span>|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|<span data-ttu-id="c7f34-124">Reprezentuje element główny dla <xref:System.Runtime.Serialization> sekcji przestrzeni nazw i zawiera elementy dla opcji ustawień <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="c7f34-124">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7f34-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c7f34-125">Remarks</span></span>  

 <span data-ttu-id="c7f34-126">Aby uzyskać więcej informacji na temat znanych typów, zobacz <xref:System.Runtime.Serialization.DataContractSerializer> i [znane typy kontraktu danych](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="c7f34-126">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer> and [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7f34-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c7f34-127">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [<span data-ttu-id="c7f34-128">Znane typy kontraktów danych</span><span class="sxs-lookup"><span data-stu-id="c7f34-128">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
