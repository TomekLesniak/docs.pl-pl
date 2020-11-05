---
title: Dodawanie elementów, atrybutów i węzłów do drzewa XML — LINQ to XML
description: Dowiedz się, jak dodać zawartość (elementy, atrybuty, komentarze, instrukcje przetwarzania, tekst i CDATA) do drzewa XML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: db911e4f-40aa-499a-9500-a9763bb6df56
ms.openlocfilehash: 272605982bb7f5e6569ff2aa0ceb990f9c3b2d42
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400845"
---
# <a name="add-elements-attributes-and-nodes-to-an-xml-tree-linq-to-xml"></a><span data-ttu-id="8a25b-103">Dodawanie elementów, atrybutów i węzłów do drzewa XML (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="8a25b-103">Add elements, attributes, and nodes to an XML tree (LINQ to XML)</span></span>

<span data-ttu-id="8a25b-104">Możesz dodać zawartość (elementy, atrybuty, komentarze, instrukcje przetwarzania, tekst i CDATA) do drzewa XML.</span><span class="sxs-lookup"><span data-stu-id="8a25b-104">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an XML tree.</span></span>

## <a name="methods-for-adding-content"></a><span data-ttu-id="8a25b-105">Metody dodawania zawartości</span><span class="sxs-lookup"><span data-stu-id="8a25b-105">Methods for adding content</span></span>

<span data-ttu-id="8a25b-106">Następujące metody dodają zawartość podrzędną do elementu <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XDocument> :</span><span class="sxs-lookup"><span data-stu-id="8a25b-106">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>

|<span data-ttu-id="8a25b-107">Metoda</span><span class="sxs-lookup"><span data-stu-id="8a25b-107">Method</span></span>|<span data-ttu-id="8a25b-108">Opis</span><span class="sxs-lookup"><span data-stu-id="8a25b-108">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="8a25b-109">Dodaje zawartość na końcu zawartości podrzędnej <xref:System.Xml.Linq.XContainer> .</span><span class="sxs-lookup"><span data-stu-id="8a25b-109">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="8a25b-110">Dodaje zawartość na początku zawartości podrzędnej <xref:System.Xml.Linq.XContainer> .</span><span class="sxs-lookup"><span data-stu-id="8a25b-110">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|

<span data-ttu-id="8a25b-111">Poniższe metody dodają zawartość jako węzły równorzędne <xref:System.Xml.Linq.XNode> .</span><span class="sxs-lookup"><span data-stu-id="8a25b-111">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="8a25b-112">Najbardziej typowym węzłem, do którego dodawana jest zawartość elementu równorzędnego <xref:System.Xml.Linq.XElement> , jest, chociaż można dodać prawidłową zawartość równorzędną do innych typów węzłów, takich jak <xref:System.Xml.Linq.XText> lub <xref:System.Xml.Linq.XComment> .</span><span class="sxs-lookup"><span data-stu-id="8a25b-112">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>

|<span data-ttu-id="8a25b-113">Metoda</span><span class="sxs-lookup"><span data-stu-id="8a25b-113">Method</span></span>|<span data-ttu-id="8a25b-114">Opis</span><span class="sxs-lookup"><span data-stu-id="8a25b-114">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="8a25b-115">Dodaje zawartość po <xref:System.Xml.Linq.XNode> .</span><span class="sxs-lookup"><span data-stu-id="8a25b-115">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="8a25b-116">Dodaje zawartość przed <xref:System.Xml.Linq.XNode> .</span><span class="sxs-lookup"><span data-stu-id="8a25b-116">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|

## <a name="example-create-two-xml-trees-and-modify-one-of-them"></a><span data-ttu-id="8a25b-117">Przykład: Utwórz dwa drzewa XML i zmodyfikuj jeden z nich</span><span class="sxs-lookup"><span data-stu-id="8a25b-117">Example: Create two XML trees and modify one of them</span></span>

<span data-ttu-id="8a25b-118">Poniższy przykład tworzy dwa drzewa XML, a następnie modyfikuje jeden z nich.</span><span class="sxs-lookup"><span data-stu-id="8a25b-118">The following example creates two XML trees, and then modifies one of them.</span></span>

```csharp
var srcTree = new XElement("Root",
    new XElement("Element1", 1),
    new XElement("Element2", 2),
    new XElement("Element3", 3),
    new XElement("Element4", 4),
    new XElement("Element5", 5)
);
var xmlTree = new XElement("Root",
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
Dim srcTree As XElement =
    <Root>
        <Element1>1</Element1>
        <Element2>2</Element2>
        <Element3>3</Element3>
        <Element4>4</Element4>
        <Element5>5</Element5>
    </Root>
Dim xmlTree As XElement =
    <Root>
        <Child1>1</Child1>
        <Child2>2</Child2>
        <Child3>3</Child3>
        <Child4>4</Child4>
        <Child5>5</Child5>
    </Root>

xmlTree.Add(<NewChild>new content</NewChild>)
xmlTree.Add(
    From el In srcTree.Elements()
    Where CInt(el) > 3
    Select el)

' Even though Child9 doesn't exist in srcTree, the following statement
' won't throw an exception, and nothing will be added to xmlTree.
xmlTree.Add(srcTree.Element("Child9"))
Console.WriteLine(xmlTree)
```

<span data-ttu-id="8a25b-119">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="8a25b-119">This example produces the following output:</span></span>

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
