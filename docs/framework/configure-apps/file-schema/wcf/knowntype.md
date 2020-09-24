---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 6bb6a419d863172951d82a67de044cb8cfc30f49
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183796"
---
# \<knownType>

<span data-ttu-id="4da6f-101">Określa typ, który ma być używany przez program <xref:System.Runtime.Serialization.DataContractSerializer> podczas deserializacji.</span><span class="sxs-lookup"><span data-stu-id="4da6f-101">Specifies a type to be used by <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="4da6f-102">Element określa "znany typ", który jest zwracany przez pole lub właściwość "zadeklarowanego typu".</span><span class="sxs-lookup"><span data-stu-id="4da6f-102">The element specifies a "known type" that is returned by a field or property of a "declared type."</span></span> <span data-ttu-id="4da6f-103">Aby uzyskać więcej informacji, zobacz [znane typy kontraktu danych](../../../wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="4da6f-103">For more information, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<knownType>**  
  
## <a name="syntax"></a><span data-ttu-id="4da6f-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4da6f-104">Syntax</span></span>  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a><span data-ttu-id="4da6f-105">Typ</span><span class="sxs-lookup"><span data-stu-id="4da6f-105">Type</span></span>  

 `string`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4da6f-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="4da6f-106">Attributes and Elements</span></span>  

 <span data-ttu-id="4da6f-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="4da6f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4da6f-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="4da6f-108">Attributes</span></span>  
  
|<span data-ttu-id="4da6f-109">Atrybut</span><span class="sxs-lookup"><span data-stu-id="4da6f-109">Attribute</span></span>|<span data-ttu-id="4da6f-110">Opis</span><span class="sxs-lookup"><span data-stu-id="4da6f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4da6f-111">typ</span><span class="sxs-lookup"><span data-stu-id="4da6f-111">type</span></span>|<span data-ttu-id="4da6f-112">Określa typ (w tym przestrzeń nazw), nazwę zestawu, wersję, kulturę i token klucza publicznego.</span><span class="sxs-lookup"><span data-stu-id="4da6f-112">Specifies the type (including namespace), assembly name, version, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4da6f-113">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="4da6f-113">Child Elements</span></span>  
  
|<span data-ttu-id="4da6f-114">Element</span><span class="sxs-lookup"><span data-stu-id="4da6f-114">Element</span></span>|<span data-ttu-id="4da6f-115">Opis</span><span class="sxs-lookup"><span data-stu-id="4da6f-115">Description</span></span>|  
|-------------|-----------------|  
|[\<parameter>](parameter.md)|<span data-ttu-id="4da6f-116">Określa indeks parametru, gdy zadeklarowany typ jest typem ogólnym.</span><span class="sxs-lookup"><span data-stu-id="4da6f-116">Specifies a parameter index when the declared type is a generic type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4da6f-117">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="4da6f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4da6f-118">Element</span><span class="sxs-lookup"><span data-stu-id="4da6f-118">Element</span></span>|<span data-ttu-id="4da6f-119">Opis</span><span class="sxs-lookup"><span data-stu-id="4da6f-119">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|<span data-ttu-id="4da6f-120">Dodaje zadeklarowany typ do kolekcji zadeklarowanych typów.</span><span class="sxs-lookup"><span data-stu-id="4da6f-120">Adds a declared type to the collection of declared types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4da6f-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4da6f-121">Remarks</span></span>  

 <span data-ttu-id="4da6f-122">Aby uzyskać więcej informacji na temat znanych typów, zobacz [znane typy kontraktu danych](../../../wcf/feature-details/data-contract-known-types.md) i <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="4da6f-122">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="4da6f-123">Zobacz, [\<dataContractSerializer>](datacontractserializer-element.md) Aby zapoznać się z przykładem użycia tego elementu.</span><span class="sxs-lookup"><span data-stu-id="4da6f-123">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4da6f-124">Przykład</span><span class="sxs-lookup"><span data-stu-id="4da6f-124">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL"/>
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="4da6f-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4da6f-125">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="4da6f-126">Znane typy kontraktów danych</span><span class="sxs-lookup"><span data-stu-id="4da6f-126">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
