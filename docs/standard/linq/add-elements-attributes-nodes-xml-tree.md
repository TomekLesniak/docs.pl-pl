---
title: Dodawanie elementów, atrybutów i węzłów do drzewa XML — LINQ to XML
description: Dowiedz się, jak dodać zawartość (elementy, atrybuty, komentarze, instrukcje przetwarzania, tekst i CDATA) do drzewa XML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: db911e4f-40aa-499a-9500-a9763bb6df56
ms.openlocfilehash: 5225560a3f3c94dcb7d4c65e66accddcead84b70
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553560"
---
# <a name="add-elements-attributes-and-nodes-to-an-xml-tree-linq-to-xml"></a>Dodawanie elementów, atrybutów i węzłów do drzewa XML (LINQ to XML)

Możesz dodać zawartość (elementy, atrybuty, komentarze, instrukcje przetwarzania, tekst i CDATA) do drzewa XML.

## <a name="methods-for-adding-content"></a>Metody dodawania zawartości

Następujące metody dodają zawartość podrzędną do elementu <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XDocument> :

|Metoda|Opis|
|------------|-----------------|
|<xref:System.Xml.Linq.XContainer.Add%2A>|Dodaje zawartość na końcu zawartości podrzędnej <xref:System.Xml.Linq.XContainer> .|
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|Dodaje zawartość na początku zawartości podrzędnej <xref:System.Xml.Linq.XContainer> .|

Poniższe metody dodają zawartość jako węzły równorzędne <xref:System.Xml.Linq.XNode> . Najbardziej typowym węzłem, do którego dodawana jest zawartość elementu równorzędnego <xref:System.Xml.Linq.XElement> , jest, chociaż można dodać prawidłową zawartość równorzędną do innych typów węzłów, takich jak <xref:System.Xml.Linq.XText> lub <xref:System.Xml.Linq.XComment> .

|Metoda|Opis|
|------------|-----------------|
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|Dodaje zawartość po <xref:System.Xml.Linq.XNode> .|
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|Dodaje zawartość przed <xref:System.Xml.Linq.XNode> .|

## <a name="example-create-two-xml-trees-and-modify-one-of-them"></a>Przykład: Utwórz dwa drzewa XML i zmodyfikuj jeden z nich

Poniższy przykład tworzy dwa drzewa XML, a następnie modyfikuje jeden z nich.

```csharp
XElement srcTree = new XElement("Root",
    new XElement("Element1", 1),
    new XElement("Element2", 2),
    new XElement("Element3", 3),
    new XElement("Element4", 4),
    new XElement("Element5", 5)
);
XElement xmlTree = new XElement("Root",
    new XElement("Child1", 1),
    new XElement("Child2", 2),
    new XElement("Child3", 3),
    new XElement("Child4", 4),
    new XElement("Child5", 5)
);
xmlTree.Add(new XElement("NewChild", "new content"));
xmlTree.Add(
    from el in srcTree.Elements()
    where (int)el > 3
    select el
);
// Even though Child9 doesn't exist in srcTree, the following statement won't
// throw an exception, and nothing will be added to xmlTree.
xmlTree.Add(srcTree.Element("Child9"));
Console.WriteLine(xmlTree);
```

```vb
Dim srcTree As XElement = _
    <Root>
        <Element1>1</Element1>
        <Element2>2</Element2>
        <Element3>3</Element3>
        <Element4>4</Element4>
        <Element5>5</Element5>
    </Root>
Dim xmlTree As XElement = _
    <Root>
        <Child1>1</Child1>
        <Child2>2</Child2>
        <Child3>3</Child3>
        <Child4>4</Child4>
        <Child5>5</Child5>
    </Root>

xmlTree.Add(<NewChild>new content</NewChild>)
xmlTree.Add( _
    From el In srcTree.Elements() _
    Where CInt(el) > 3 _
    Select el)

' Even though Child9 doesn't exist in srcTree, the following statement
' won't throw an exception, and nothing will be added to xmlTree.
xmlTree.Add(srcTree.Element("Child9"))
Console.WriteLine(xmlTree)
```

Ten przykład generuje następujące wyniki:

```xml
<Root>
  <Child1>1</Child1>
  <Child2>2</Child2>
  <Child3>3</Child3>
  <Child4>4</Child4>
  <Child5>5</Child5>
  <NewChild>new content</NewChild>
  <Element4>4</Element4>
  <Element5>5</Element5>
</Root>
```
