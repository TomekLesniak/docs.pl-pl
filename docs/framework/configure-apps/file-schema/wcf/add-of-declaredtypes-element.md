---
title: <add><declaredTypes>elementu
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 9af47848b03074ec88f38a5884089bc50239ee50
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201671"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="36e1b-102">\<add>\<declaredTypes>elementu</span><span class="sxs-lookup"><span data-stu-id="36e1b-102">\<add> of \<declaredTypes> Element</span></span>

<span data-ttu-id="36e1b-103">Dodaje typ używany przez <xref:System.Runtime.Serialization.DataContractSerializer> podczas deserializacji.</span><span class="sxs-lookup"><span data-stu-id="36e1b-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="36e1b-104">Każdy zadeklarowany typ zawiera znane typy, które będą zwracane jako pole lub właściwość zadeklarowanego typu.</span><span class="sxs-lookup"><span data-stu-id="36e1b-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="36e1b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="36e1b-105">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36e1b-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="36e1b-106">Attributes and Elements</span></span>  

 <span data-ttu-id="36e1b-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="36e1b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36e1b-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="36e1b-108">Attributes</span></span>  
  
|<span data-ttu-id="36e1b-109">Atrybut</span><span class="sxs-lookup"><span data-stu-id="36e1b-109">Attribute</span></span>|<span data-ttu-id="36e1b-110">Opis</span><span class="sxs-lookup"><span data-stu-id="36e1b-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="36e1b-111">typ</span><span class="sxs-lookup"><span data-stu-id="36e1b-111">type</span></span>|<span data-ttu-id="36e1b-112">Wymagany atrybut ciągu.</span><span class="sxs-lookup"><span data-stu-id="36e1b-112">Required string attribute.</span></span><br /><br /> <span data-ttu-id="36e1b-113">Określa nazwę typu (w tym przestrzeń nazw), nazwę zestawu, numer wersji, kulturę i token klucza publicznego.</span><span class="sxs-lookup"><span data-stu-id="36e1b-113">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36e1b-114">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="36e1b-114">Child Elements</span></span>  
  
|<span data-ttu-id="36e1b-115">Element</span><span class="sxs-lookup"><span data-stu-id="36e1b-115">Element</span></span>|<span data-ttu-id="36e1b-116">Opis</span><span class="sxs-lookup"><span data-stu-id="36e1b-116">Description</span></span>|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|<span data-ttu-id="36e1b-117">Określa znany typ zadeklarowanego typu, który jest dodawany.</span><span class="sxs-lookup"><span data-stu-id="36e1b-117">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="36e1b-118">Jeśli zadeklarowany typ jest typem ogólnym, należy również dodać element parametru do `<knownType>` elementu, aby określić, który parametr generyczny jest używany do zwrócenia znanego typu.</span><span class="sxs-lookup"><span data-stu-id="36e1b-118">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36e1b-119">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="36e1b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="36e1b-120">Element</span><span class="sxs-lookup"><span data-stu-id="36e1b-120">Element</span></span>|<span data-ttu-id="36e1b-121">Opis</span><span class="sxs-lookup"><span data-stu-id="36e1b-121">Description</span></span>|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|<span data-ttu-id="36e1b-122">Zawiera typy, które wymagają znanych typów podczas deserializacji przez <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="36e1b-122">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36e1b-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="36e1b-123">Remarks</span></span>  

 <span data-ttu-id="36e1b-124">Aby uzyskać więcej informacji na temat znanych typów, zobacz [znane typy kontraktu danych](../../../wcf/feature-details/data-contract-known-types.md) i <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="36e1b-124">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="36e1b-125">Zobacz, [\<dataContractSerializer>](datacontractserializer-element.md) Aby zapoznać się z przykładem użycia tego elementu.</span><span class="sxs-lookup"><span data-stu-id="36e1b-125">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="36e1b-126">Jeśli typ zostanie dodany <xref:System.Object> jako `<declaredType>` , <xref:System.Configuration.ConfigurationErrorsException> zostanie zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="36e1b-126">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="36e1b-127">Dzieje się tak, ponieważ <xref:System.Object> Typ nie może być używany jako zadeklarowany typ w konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="36e1b-127">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36e1b-128">Przykład</span><span class="sxs-lookup"><span data-stu-id="36e1b-128">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL" />
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="36e1b-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="36e1b-129">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="36e1b-130">Znane typy kontraktów danych</span><span class="sxs-lookup"><span data-stu-id="36e1b-130">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [<span data-ttu-id="36e1b-131">\<add> z \<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="36e1b-131">\<add> of \<declaredTypes></span></span>](add-of-declaredtypes-element.md)
