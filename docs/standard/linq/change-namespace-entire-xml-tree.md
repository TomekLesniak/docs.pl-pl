---
title: Jak zmienić przestrzeń nazw dla całego drzewa XML — LINQ to XML
description: Dowiedz się, jak zmienić przestrzeń nazw dla całego drzewa XML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 1584ff3b-c77d-4241-ab62-80adfb7bfc1b
ms.openlocfilehash: ac4eda71dd536ed2f940f1e86a0190ef337c386a
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553395"
---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-linq-to-xml"></a>Jak zmienić przestrzeń nazw dla całego drzewa XML (LINQ to XML)

Czasami trzeba programistycznie zmienić przestrzeń nazw dla elementu lub atrybutu. Ułatwia to LINQ to XML. <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType>Właściwość może być ustawiona. <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType>Nie można ustawić właściwości, ale można łatwo skopiować atrybuty do <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> , usunąć istniejące atrybuty, a następnie dodać nowe atrybuty, które znajdują się w nowym żądanym obszarze nazw.

Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

## <a name="example-create-two-xml-trees-change-the-namespaces-and-combine-the-trees"></a>Przykład: Utwórz dwa drzewa XML, Zmień przestrzenie nazw i Połącz drzewa

Poniższy kod tworzy dwa drzewa XML w obszarze brak przestrzeni nazw. Następnie zmienia przestrzeń nazw każdego drzewa i łączy je w jedno drzewo.

```csharp
XElement tree1 = new XElement("Data",
    new XElement("Child", "content",
        new XAttribute("MyAttr", "content")
    )
);
XElement tree2 = new XElement("Data",
    new XElement("Child", "content",
        new XAttribute("MyAttr", "content")
    )
);
XNamespace aw = "http://www.adventure-works.com";
XNamespace ad = "http://www.adatum.com";
// Change the namespace of every element and attribute in the first tree.
foreach (XElement el in tree1.DescendantsAndSelf())
{
    el.Name = aw.GetName(el.Name.LocalName);
    List<XAttribute> atList = el.Attributes().ToList();
    el.Attributes().Remove();
    foreach (XAttribute at in atList)
        el.Add(new XAttribute(aw.GetName(at.Name.LocalName), at.Value));
}
// Change the namespace of every element and attribute in the second tree.
foreach (XElement el in tree2.DescendantsAndSelf())
{
    el.Name = ad.GetName(el.Name.LocalName);
    List<XAttribute> atList = el.Attributes().ToList();
    el.Attributes().Remove();
    foreach (XAttribute at in atList)
        el.Add(new XAttribute(ad.GetName(at.Name.LocalName), at.Value));
}
// Add attribute namespaces so that the tree will be serialized with
// the aw and ad namespace prefixes.
tree1.Add(
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com")
);
tree2.Add(
    new XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com")
);
// Create a new composite tree.
XElement root = new XElement("Root",
    tree1,
    tree2
);
Console.WriteLine(root);
```

```vb
Dim tree1 As XElement = _
    <Data>
        <Child MyAttr="content">content</Child>
    </Data>
Dim tree2 As XElement = _
    <Data>
        <Child MyAttr="content">content</Child>
    </Data>
Dim aw As XNamespace = "http://www.adventure-works.com"
Dim ad As XNamespace = "http://www.adatum.com"
' Change the namespace of every element and attribute in the first tree.
For Each el As XElement In tree1.DescendantsAndSelf
    el.Name = aw.GetName(el.Name.LocalName)
    Dim atList As List(Of XAttribute) = el.Attributes().ToList()
    el.Attributes().Remove()
    For Each at As XAttribute In atList
        el.Add(New XAttribute(aw.GetName(at.Name.LocalName), at.Value))
    Next
Next
' Change the namespace of every element and attribute in the second tree.
For Each el As XElement In tree2.DescendantsAndSelf()
    el.Name = ad.GetName(el.Name.LocalName)
    Dim atList As List(Of XAttribute) = el.Attributes().ToList()
    el.Attributes().Remove()
    For Each at As XAttribute In atList
        el.Add(New XAttribute(ad.GetName(at.Name.LocalName), at.Value))
    Next
Next
' Add attribute namespaces so that the tree will be serialized with
' the aw and ad namespace prefixes.
tree1.Add( _
    New XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com") _
)
tree2.Add( _
    New XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com") _
)
' Create a new composite tree.
Dim root As XElement = _
    <Root>
        <%= tree1 %>
        <%= tree2 %>
    </Root>
Console.WriteLine(root)
```

Ten przykład generuje następujące wyniki:

```xml
<Root>
  <aw:Data xmlns:aw="http://www.adventure-works.com">
    <aw:Child aw:MyAttr="content">content</aw:Child>
  </aw:Data>
  <ad:Data xmlns:ad="http://www.adatum.com">
    <ad:Child ad:MyAttr="content">content</ad:Child>
  </ad:Data>
</Root>
```
