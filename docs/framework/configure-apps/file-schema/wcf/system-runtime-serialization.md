---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: 84ced06691ce3b3c9c9573fc9d114335096a849d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157112"
---
# \<system.runtime.serialization>

<span data-ttu-id="c163a-102">Reprezentuje element główny dla <xref:System.Runtime.Serialization> sekcji przestrzeni nazw i zawiera elementy dla opcji ustawień <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="c163a-102">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.serialization>**  
  
## <a name="syntax"></a><span data-ttu-id="c163a-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="c163a-103">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c163a-104">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="c163a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="c163a-105">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="c163a-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c163a-106">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="c163a-106">Attributes</span></span>  

 <span data-ttu-id="c163a-107">Brak.</span><span class="sxs-lookup"><span data-stu-id="c163a-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c163a-108">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="c163a-108">Child Elements</span></span>  
  
|<span data-ttu-id="c163a-109">Element</span><span class="sxs-lookup"><span data-stu-id="c163a-109">Element</span></span>|<span data-ttu-id="c163a-110">Opis</span><span class="sxs-lookup"><span data-stu-id="c163a-110">Description</span></span>|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="c163a-111">Umożliwia dodanie znanych typów, które mają być używane podczas deserializacji.</span><span class="sxs-lookup"><span data-stu-id="c163a-111">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c163a-112">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="c163a-112">Parent Elements</span></span>  
  
|<span data-ttu-id="c163a-113">Element</span><span class="sxs-lookup"><span data-stu-id="c163a-113">Element</span></span>|<span data-ttu-id="c163a-114">Opis</span><span class="sxs-lookup"><span data-stu-id="c163a-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c163a-115">\<configuration> Postaci</span><span class="sxs-lookup"><span data-stu-id="c163a-115">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="c163a-116">Element najwyższego poziomu dla konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c163a-116">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c163a-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c163a-117">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="c163a-118">Używanie kontraktów danych</span><span class="sxs-lookup"><span data-stu-id="c163a-118">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="c163a-119">Znane typy kontraktów danych</span><span class="sxs-lookup"><span data-stu-id="c163a-119">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
