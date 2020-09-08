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
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-linq-to-xml"></a><span data-ttu-id="6fe67-103">Jak zmienić przestrzeń nazw dla całego drzewa XML (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="6fe67-103">How to change the namespace for an entire XML tree (LINQ to XML)</span></span>

<span data-ttu-id="6fe67-104">Czasami trzeba programistycznie zmienić przestrzeń nazw dla elementu lub atrybutu.</span><span class="sxs-lookup"><span data-stu-id="6fe67-104">You sometimes have to programmatically change the namespace for an element or an attribute.</span></span> <span data-ttu-id="6fe67-105">Ułatwia to LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="6fe67-105">LINQ to XML makes this easy.</span></span> <span data-ttu-id="6fe67-106"><xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType>Właściwość może być ustawiona.</span><span class="sxs-lookup"><span data-stu-id="6fe67-106">The <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> property can be set.</span></span> <span data-ttu-id="6fe67-107"><xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType>Nie można ustawić właściwości, ale można łatwo skopiować atrybuty do <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> , usunąć istniejące atrybuty, a następnie dodać nowe atrybuty, które znajdują się w nowym żądanym obszarze nazw.</span><span class="sxs-lookup"><span data-stu-id="6fe67-107">The <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> property can't be set, but you can easily copy the attributes into a <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, remove the existing attributes, and then add new attributes that are in the new desired namespace.</span></span>

<span data-ttu-id="6fe67-108">Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6fe67-108">For more information, see [Namespaces overview](namespaces-overview.md).</span></span>

## <a name="example-create-two-xml-trees-change-the-namespaces-and-combine-the-trees"></a><span data-ttu-id="6fe67-109">Przykład: Utwórz dwa drzewa XML, Zmień przestrzenie nazw i Połącz drzewa</span><span class="sxs-lookup"><span data-stu-id="6fe67-109">Example: Create two XML trees, change the namespaces, and combine the trees</span></span>

<span data-ttu-id="6fe67-110">Poniższy kod tworzy dwa drzewa XML w obszarze brak przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="6fe67-110">The following code creates two XML trees in no namespace.</span></span> <span data-ttu-id="6fe67-111">Następnie zmienia przestrzeń nazw każdego drzewa i łączy je w jedno drzewo.</span><span class="sxs-lookup"><span data-stu-id="6fe67-111">It then changes the namespace of each of the trees, and combines them into a single tree.</span></span>

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

<span data-ttu-id="6fe67-112">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="6fe67-112">This example produces the following output:</span></span>

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
