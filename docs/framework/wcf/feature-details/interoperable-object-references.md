---
title: Odwołania do obiektów międzyoperacyjnych
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: bf395c187c46e88406bfb81798c7e359b48255e3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263233"
---
# <a name="interoperable-object-references"></a><span data-ttu-id="d3ee5-102">Odwołania do obiektów międzyoperacyjnych</span><span class="sxs-lookup"><span data-stu-id="d3ee5-102">Interoperable object references</span></span>

<span data-ttu-id="d3ee5-103">Domyślnie <xref:System.Runtime.Serialization.DataContractSerializer> serializacji obiektów według wartości.</span><span class="sxs-lookup"><span data-stu-id="d3ee5-103">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="d3ee5-104">Możesz użyć właściwości, <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> aby nakazać serializatorowi kontraktu danych zachowanie odwołań do obiektów podczas serializacji obiektów.</span><span class="sxs-lookup"><span data-stu-id="d3ee5-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="d3ee5-105">Wygenerowany kod XML</span><span class="sxs-lookup"><span data-stu-id="d3ee5-105">Generated XML</span></span>  

 <span data-ttu-id="d3ee5-106">Na przykład rozważmy następujący obiekt:</span><span class="sxs-lookup"><span data-stu-id="d3ee5-106">As an example, consider the following object:</span></span>  
  
```csharp  
[DataContract]  
public class X  
{  
    SomeClass someInstance = new SomeClass();  
    [DataMember]  
    public SomeClass A = someInstance;  
    [DataMember]  
    public SomeClass B = someInstance;  
}  
  
public class SomeClass
{  
}  
```  
  
 <span data-ttu-id="d3ee5-107">W przypadku <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> wybrania wartości `false` (domyślnie) jest generowany następujący kod XML:</span><span class="sxs-lookup"><span data-stu-id="d3ee5-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="d3ee5-108">W przypadku <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> wybrania opcji `true` :</span><span class="sxs-lookup"><span data-stu-id="d3ee5-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="d3ee5-109">Jednak program <xref:System.Runtime.Serialization.XsdDataContractExporter> nie opisuje `id` atrybutów i `ref` w jego schemacie, nawet gdy `preserveObjectReferences` Właściwość jest ustawiona na `true` .</span><span class="sxs-lookup"><span data-stu-id="d3ee5-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="d3ee5-110">Używanie IsReference</span><span class="sxs-lookup"><span data-stu-id="d3ee5-110">Using IsReference</span></span>  

 <span data-ttu-id="d3ee5-111">Aby wygenerować informacje referencyjne obiektu, które są prawidłowe zgodnie ze schematem opisującym go, Zastosuj <xref:System.Runtime.Serialization.DataContractAttribute> atrybut do typu i ustaw <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flagę na `true` .</span><span class="sxs-lookup"><span data-stu-id="d3ee5-111">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="d3ee5-112">Poniższy przykład modyfikuje klasę `X` w poprzednim przykładzie poprzez dodanie `IsReference` :</span><span class="sxs-lookup"><span data-stu-id="d3ee5-112">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
```csharp
[DataContract(IsReference=true)]
public class X
{  
     SomeClass someInstance = new SomeClass();
     [DataMember]
     public SomeClass A = someInstance;
     [DataMember]
     public SomeClass B = someInstance;
}
  
public class SomeClass
{
}  
````

 <span data-ttu-id="d3ee5-113">Wygenerowany kod XML jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d3ee5-113">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="d3ee5-114">Użycie `IsReference` zapewnia zgodność z komunikatem o dwukierunkowym wyzwoleniu.</span><span class="sxs-lookup"><span data-stu-id="d3ee5-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="d3ee5-115">Bez tego, gdy typ jest generowany ze schematu, dane wyjściowe XML dla tego typu nie muszą być zgodne ze schematem przyjętym pierwotnie.</span><span class="sxs-lookup"><span data-stu-id="d3ee5-115">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="d3ee5-116">Innymi słowy, chociaż `id` `ref` atrybuty i były serializowane, oryginalny schemat może mieć wykluczone atrybuty (lub wszystkie atrybuty) w kodzie XML.</span><span class="sxs-lookup"><span data-stu-id="d3ee5-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="d3ee5-117">`IsReference`Po zastosowaniu do elementu członkowskiego danych, członek nadal jest rozpoznawany jako *referencyjny* w przypadku wyłącznika.</span><span class="sxs-lookup"><span data-stu-id="d3ee5-117">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ee5-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d3ee5-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
