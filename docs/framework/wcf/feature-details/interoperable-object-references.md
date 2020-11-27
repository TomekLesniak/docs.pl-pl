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
# <a name="interoperable-object-references"></a>Odwołania do obiektów międzyoperacyjnych

Domyślnie <xref:System.Runtime.Serialization.DataContractSerializer> serializacji obiektów według wartości. Możesz użyć właściwości, <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> aby nakazać serializatorowi kontraktu danych zachowanie odwołań do obiektów podczas serializacji obiektów.  
  
## <a name="generated-xml"></a>Wygenerowany kod XML  

 Na przykład rozważmy następujący obiekt:  
  
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
  
 W przypadku <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> wybrania wartości `false` (domyślnie) jest generowany następujący kod XML:  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 W przypadku <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> wybrania opcji `true` :  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 Jednak program <xref:System.Runtime.Serialization.XsdDataContractExporter> nie opisuje `id` atrybutów i `ref` w jego schemacie, nawet gdy `preserveObjectReferences` Właściwość jest ustawiona na `true` .  
  
## <a name="using-isreference"></a>Używanie IsReference  

 Aby wygenerować informacje referencyjne obiektu, które są prawidłowe zgodnie ze schematem opisującym go, Zastosuj <xref:System.Runtime.Serialization.DataContractAttribute> atrybut do typu i ustaw <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flagę na `true` . Poniższy przykład modyfikuje klasę `X` w poprzednim przykładzie poprzez dodanie `IsReference` :  
  
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

 Wygenerowany kod XML jest następujący:  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 Użycie `IsReference` zapewnia zgodność z komunikatem o dwukierunkowym wyzwoleniu. Bez tego, gdy typ jest generowany ze schematu, dane wyjściowe XML dla tego typu nie muszą być zgodne ze schematem przyjętym pierwotnie. Innymi słowy, chociaż `id` `ref` atrybuty i były serializowane, oryginalny schemat może mieć wykluczone atrybuty (lub wszystkie atrybuty) w kodzie XML. `IsReference`Po zastosowaniu do elementu członkowskiego danych, członek nadal jest rozpoznawany jako *referencyjny* w przypadku wyłącznika.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
