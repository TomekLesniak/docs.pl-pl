---
title: Jak pobrać pojedynczy atrybut-LINQ to XML
description: Pobierz pojedynczy atrybut elementu pod nazwą atrybutu.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 1b6b07b9-933f-47e9-874e-e790cab49dc5
ms.openlocfilehash: a8a56ec62275f2376d19d7fc9090414b74fc77ad
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553660"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml"></a>Pobieranie pojedynczego atrybutu (LINQ to XML)

W tym artykule wyjaśniono, jak pobrać pojedynczy atrybut elementu, pod nazwą atrybutu. Jest to przydatne w przypadku pisania wyrażeń zapytania, gdzie chcesz znaleźć element, który ma określony atrybut.

<xref:System.Xml.Linq.XElement.Attribute%2A>Metoda <xref:System.Xml.Linq.XElement> klasy zwraca <xref:System.Xml.Linq.XAttribute> z określoną nazwą.

## <a name="example-retrieve-attribute-values-given-the-element-and-attribute-names"></a>Przykład: pobieranie wartości atrybutów, z uwzględnieniem nazw elementów i atrybutów

Poniższy przykład używa <xref:System.Xml.Linq.XElement> metody do utworzenia elementu o nazwie `PhoneNumbers` . Następnie znajduje wszystkie elementy podrzędne o nazwie `Phone` i, dla każdego, używa <xref:System.Xml.Linq.XElement.Attribute%2A> metody do uzyskania i wyprowadzenia wartości atrybutu o nazwie `type` :

```csharp
XElement cust = new XElement("PhoneNumbers",
    new XElement("Phone",
        new XAttribute("type", "home"),
        "555-555-5555"),
    new XElement("Phone",
        new XAttribute("type", "work"),
        "555-555-6666")
);
IEnumerable<XElement> elList =
    from el in cust.Descendants("Phone")
    select el;
foreach (XElement el in elList)
    Console.WriteLine((string)el.Attribute("type"));
```

```vb
Dim cust As XElement = <PhoneNumbers>
                           <Phone type="home">555-555-5555</Phone>
                           <Phone type="work">555-555-6666</Phone>
                       </PhoneNumbers>
Dim elList = From el In cust...<Phone>
For Each e As XElement In elList
    Console.WriteLine(e.@type)
Next
```

Ten przykład generuje następujące wyniki:

```output
home
work
```

## <a name="example-retrieve-an-attribute-value-with-a-cast"></a>Przykład: pobieranie wartości atrybutu z rzutowania

Możesz pobrać wartość atrybutu poprzez jego rzutowanie, tak jak w przypadku <xref:System.Xml.Linq.XElement> obiektów. Poniższy przykład ilustruje:

```csharp
XElement cust = new XElement("PhoneNumbers",
    new XElement("Phone",
        new XAttribute("type", "home"),
        "555-555-5555"),
    new XElement("Phone",
        new XAttribute("type", "work"),
        "555-555-6666")
);
IEnumerable<XElement> elList =
    from el in cust.Descendants("Phone")
    select el;
foreach (XElement el in elList)
    Console.WriteLine((string)el.Attribute("type"));
```

```vb
Dim cust As XElement = <PhoneNumbers>
                           <Phone type="home">555-555-5555</Phone>
                           <Phone type="work">555-555-6666</Phone>
                       </PhoneNumbers>
Dim elList As IEnumerable(Of XElement) = _
    From el In cust...<Phone> _
    Select el
For Each el As XElement In elList
    Console.WriteLine(el.@type)
Next
```

Ten przykład generuje następujące wyniki:

```output
home
work
```

LINQ to XML zapewnia jawne Operatory rzutowania dla klasy do,,,,,,,,, <xref:System.Xml.Linq.XAttribute> `string` `bool` `bool?` `int` `int?` `uint` `uint?` `long` `long?` `ulong` , `ulong?` , `float` , `float?` `double` `double?` `decimal` `decimal?` `DateTime` `DateTime?` `TimeSpan` `TimeSpan?` `GUID` `GUID?` ,,,,,,,,,, i.

## <a name="example-cast-for-an-attribute-in-a-namespace"></a>Przykład: Rzutowanie atrybutu w przestrzeni nazw

Poniższy przykład pokazuje ten sam kod dla atrybutu, który znajduje się w przestrzeni nazw. Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

```csharp
XNamespace aw = "http://www.adventure-works.com";
XElement cust = new XElement(aw + "PhoneNumbers",
    new XElement(aw + "Phone",
        new XAttribute(aw + "type", "home"),
        "555-555-5555"),
    new XElement(aw + "Phone",
        new XAttribute(aw + "type", "work"),
        "555-555-6666")
);
IEnumerable<XElement> elList =
    from el in cust.Descendants(aw + "Phone")
    select el;
foreach (XElement el in elList)
    Console.WriteLine((string)el.Attribute(aw + "type"));
```

```vb
Imports <xmlns:aw="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim cust As XElement = _
            <aw:PhoneNumbers>
                <aw:Phone aw:type="home">555-555-5555</aw:Phone>
                <aw:Phone aw:type="work">555-555-6666</aw:Phone>
            </aw:PhoneNumbers>
        Dim elList As IEnumerable(Of XElement) = _
            From el In cust...<aw:Phone> _
            Select el
        For Each el As XElement In elList
            Console.WriteLine(el.@aw:type)
        Next
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```output
home
work
```

## <a name="see-also"></a>Zobacz też

- [Przegląd osi LINQ to XML](linq-xml-axes-overview.md)
