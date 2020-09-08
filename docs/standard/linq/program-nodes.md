---
title: Programowanie z węzłami — LINQ to XML
description: Dowiedz się, jak kodować na poziomie węzła drzewa XML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: c38df0f2-c805-431a-93ff-9103a4284c2f
ms.openlocfilehash: 8f9d5c8656a06a9b40a3833aaf7e190b9ba3f0a6
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553283"
---
# <a name="programming-with-nodes-linq-to-xml"></a><span data-ttu-id="1bb36-103">Programowanie z węzłami (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="1bb36-103">Programming with nodes (LINQ to XML)</span></span>

<span data-ttu-id="1bb36-104">LINQ to XML deweloperzy, którzy muszą pisać programy takie jak Edytor XML, system transformacji lub moduł zapisujący raport często potrzebują kodu, który działa na tym samym poziomie szczegółowości niż elementy i atrybuty.</span><span class="sxs-lookup"><span data-stu-id="1bb36-104">LINQ to XML developers who need to write programs such as an XML editor, a transform system, or a report writer often need code that works at a finer level of granularity than elements and attributes.</span></span> <span data-ttu-id="1bb36-105">Często wymagają one pracy na poziomie węzła, manipulowania węzłami tekstowymi, instrukcjami przetwarzania i komentarzami przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="1bb36-105">They often need to work at the node level, manipulating text nodes, processing instructions, and processing comments.</span></span> <span data-ttu-id="1bb36-106">Ten artykuł zawiera informacje na temat programowania na poziomie węzła.</span><span class="sxs-lookup"><span data-stu-id="1bb36-106">This article provides information about programming at the node level.</span></span>

## <a name="example-the-parent-property-values-of-the-child-nodes-of-xdocument-are-set-to-null"></a><span data-ttu-id="1bb36-107">Przykład: `Parent` wartości właściwości węzłów podrzędnych klasy XDocument są ustawione na wartość `null`</span><span class="sxs-lookup"><span data-stu-id="1bb36-107">Example: The `Parent` property values of the child nodes of XDocument are set to `null`</span></span>

<span data-ttu-id="1bb36-108"><xref:System.Xml.Linq.XObject.Parent%2A>Właściwość zawiera element nadrzędny <xref:System.Xml.Linq.XElement> , a nie węzeł nadrzędny.</span><span class="sxs-lookup"><span data-stu-id="1bb36-108">The <xref:System.Xml.Linq.XObject.Parent%2A> property contains the parent <xref:System.Xml.Linq.XElement>, not the parent node.</span></span> <span data-ttu-id="1bb36-109">Węzły podrzędne <xref:System.Xml.Linq.XDocument> nie mają elementu nadrzędnego <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="1bb36-109">Child nodes of <xref:System.Xml.Linq.XDocument> have no parent <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="1bb36-110">Ich element nadrzędny jest dokumentem, więc <xref:System.Xml.Linq.XObject.Parent%2A> Właściwość dla tych węzłów jest ustawiona na `null` .</span><span class="sxs-lookup"><span data-stu-id="1bb36-110">Their parent is the document, so the <xref:System.Xml.Linq.XObject.Parent%2A> property for those nodes is set to `null`.</span></span>

<span data-ttu-id="1bb36-111">Poniższy przykład ilustruje:</span><span class="sxs-lookup"><span data-stu-id="1bb36-111">The following example demonstrates this:</span></span>

```csharp
XDocument doc = XDocument.Parse(@"<!-- a comment --><Root/>");
Console.WriteLine(doc.Nodes().OfType<XComment>().First().Parent == null);
Console.WriteLine(doc.Root.Parent == null);
```

```vb
Dim doc As XDocument = XDocument.Parse("<!-- a comment --><Root/>")
Console.WriteLine(doc.Nodes().OfType(Of XComment).First().Parent Is Nothing)
Console.WriteLine(doc.Root.Parent Is Nothing)
```

<span data-ttu-id="1bb36-112">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1bb36-112">This example produces the following output:</span></span>

```output
True
True
```

## <a name="example-adding-text-may-or-may-not-create-a-new-text-node"></a><span data-ttu-id="1bb36-113">Przykład: dodanie tekstu może być niemożliwe lub nie można utworzyć nowego węzła tekstowego</span><span class="sxs-lookup"><span data-stu-id="1bb36-113">Example: Adding text may or may not create a new text node</span></span>

<span data-ttu-id="1bb36-114">W wielu modelach programowania XML sąsiadujące węzły tekstowe są zawsze scalane.</span><span class="sxs-lookup"><span data-stu-id="1bb36-114">In a number of XML programming models, adjacent text nodes are always merged.</span></span> <span data-ttu-id="1bb36-115">Jest to czasami nazywane normalizacją węzłów tekstowych.</span><span class="sxs-lookup"><span data-stu-id="1bb36-115">This is sometimes called normalization of text nodes.</span></span> <span data-ttu-id="1bb36-116">LINQ to XML nie normalizuje węzłów tekstowych.</span><span class="sxs-lookup"><span data-stu-id="1bb36-116">LINQ to XML doesn't normalize text nodes.</span></span> <span data-ttu-id="1bb36-117">Jeśli dodasz dwa węzły tekstowe do tego samego elementu, spowoduje to sąsiednie węzły tekstowe.</span><span class="sxs-lookup"><span data-stu-id="1bb36-117">If you add two text nodes to the same element, it will result in adjacent text nodes.</span></span> <span data-ttu-id="1bb36-118">Jednakże jeśli dodasz zawartość określoną jako ciąg, a nie jako <xref:System.Xml.Linq.XText> węzeł, LINQ to XML może scalić ciąg z sąsiednim węzłem tekstowym.</span><span class="sxs-lookup"><span data-stu-id="1bb36-118">However, if you add content specified as a string rather than as an <xref:System.Xml.Linq.XText> node, LINQ to XML might merge the string with an adjacent text node.</span></span> <span data-ttu-id="1bb36-119">Poniższy przykład ilustruje to.</span><span class="sxs-lookup"><span data-stu-id="1bb36-119">The following example demonstrates this.</span></span>

```csharp
XElement xmlTree = new XElement("Root", "Content");

Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());

// this doesn't add a new text node
xmlTree.Add("new content");
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());

// this does add a new, adjacent text node
xmlTree.Add(new XText("more text"));
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());
```

```vb
Dim xmlTree As XElement = <Root>Content</Root>
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())

' This doesn't add a new text node.
xmlTree.Add("new content")
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())

'// This does add a new, adjacent text node.
xmlTree.Add(New XText("more text"))
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())
```

 <span data-ttu-id="1bb36-120">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1bb36-120">This example produces the following output:</span></span>

```output
1
1
2
```

## <a name="example-setting-a-text-node-value-to-the-empty-string-doesnt-delete-the-node"></a><span data-ttu-id="1bb36-121">Przykład: ustawienie wartości węzła tekstowego na pusty ciąg nie powoduje usunięcia węzła</span><span class="sxs-lookup"><span data-stu-id="1bb36-121">Example: Setting a text node value to the empty string doesn't delete the node</span></span>

<span data-ttu-id="1bb36-122">W niektórych modelach programowania XML węzły tekstowe są gwarantowane, że nie zawierają pustego ciągu.</span><span class="sxs-lookup"><span data-stu-id="1bb36-122">In some XML programming models, text nodes are guaranteed to not contain the empty string.</span></span> <span data-ttu-id="1bb36-123">Powodem jest to, że taki węzeł tekstowy nie ma wpływu na serializacji XML.</span><span class="sxs-lookup"><span data-stu-id="1bb36-123">The reasoning is that such a text node has no impact on serialization of the XML.</span></span> <span data-ttu-id="1bb36-124">Jednak z tego samego powodu, w którym jest możliwy sąsiednie węzły tekstowe, jeśli usuniesz tekst z węzła tekstowego przez ustawienie jego wartości na pusty ciąg, sam węzeł tekstu nie zostanie usunięty.</span><span class="sxs-lookup"><span data-stu-id="1bb36-124">However, for the same reason that adjacent text nodes are possible, if you remove the text from a text node by setting its value to the empty string, the text node itself won't be deleted.</span></span>

```csharp
XElement xmlTree = new XElement("Root", "Content");
XText textNode = xmlTree.Nodes().OfType<XText>().First();

// the following line doesn't cause the removal of the text node.
textNode.Value = "";

XText textNode2 = xmlTree.Nodes().OfType<XText>().First();
Console.WriteLine(">>{0}<<", textNode2);
```

```vb
Dim xmlTree As XElement = <Root>Content</Root>
Dim textNode As XText = xmlTree.Nodes().OfType(Of XText)().First()

' The following line doesn't cause the removal of the text node.
textNode.Value = ""

Dim textNode2 As XText = xmlTree.Nodes().OfType(Of XText)().First()
Console.WriteLine(">>{0}<<", textNode2)
```

<span data-ttu-id="1bb36-125">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1bb36-125">This example produces the following output:</span></span>

```output
>><<
```

## <a name="example-an-element-with-one-empty-text-node-is-serialized-differently-from-one-with-no-text-node"></a><span data-ttu-id="1bb36-126">Przykład: element z jednym pustym węzłem tekstowym jest serializowany inaczej niż jeden bez węzła tekstowego</span><span class="sxs-lookup"><span data-stu-id="1bb36-126">Example: An element with one empty text node is serialized differently from one with no text node</span></span>

<span data-ttu-id="1bb36-127">Jeśli element zawiera tylko podrzędny węzeł tekstowy, który jest pusty, jest serializowany z składnią długiego tagu: `<Child></Child>` .</span><span class="sxs-lookup"><span data-stu-id="1bb36-127">If an element contains only a child text node that's empty, it's serialized with the long tag syntax: `<Child></Child>`.</span></span> <span data-ttu-id="1bb36-128">Jeśli element nie zawiera żadnych węzłów podrzędnych, zostaje Zserializowany za pomocą składni krótkiej tagu: `<Child />` .</span><span class="sxs-lookup"><span data-stu-id="1bb36-128">If an element contains no child nodes whatsoever, it's serialized with the short tag syntax: `<Child />`.</span></span>

```csharp
XElement child1 = new XElement("Child1",
    new XText("")
);
XElement child2 = new XElement("Child2");
Console.WriteLine(child1);
Console.WriteLine(child2);
```

```vb
Dim child1 As XElement = New XElement("Child1", _
    New XText("") _
)
Dim child2 As XElement = New XElement("Child2")
Console.WriteLine(child1)
Console.WriteLine(child2)
```

<span data-ttu-id="1bb36-129">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1bb36-129">This example produces the following output:</span></span>

```xml
<Child1></Child1>
<Child2 />
```

## <a name="example-namespaces-are-attributes-in-the-linq-to-xml-tree"></a><span data-ttu-id="1bb36-130">Przykład: przestrzenie nazw są atrybutami w drzewie LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="1bb36-130">Example: Namespaces are attributes in the LINQ to XML tree</span></span>

<span data-ttu-id="1bb36-131">Mimo że deklaracje przestrzeni nazw mają identyczną składnię atrybutów, w niektórych interfejsach programowania, takich jak XSLT i XPath, deklaracje przestrzeni nazw nie są uważane za atrybuty.</span><span class="sxs-lookup"><span data-stu-id="1bb36-131">Even though namespace declarations have identical syntax to attributes, in some programming interfaces, such as XSLT and XPath, namespace declarations aren't considered to be attributes.</span></span> <span data-ttu-id="1bb36-132">Jednak w LINQ to XML przestrzenie nazw są przechowywane jako <xref:System.Xml.Linq.XAttribute> obiekty w drzewie XML.</span><span class="sxs-lookup"><span data-stu-id="1bb36-132">However, in LINQ to XML, namespaces are stored as <xref:System.Xml.Linq.XAttribute> objects in the XML tree.</span></span> <span data-ttu-id="1bb36-133">W przypadku iteracji przez atrybuty elementu, który zawiera deklarację przestrzeni nazw, Deklaracja przestrzeni nazw jest jednym z elementów w zwróconej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="1bb36-133">If you iterate through the attributes of an element that contains a namespace declaration, the namespace declaration is one of the items in the returned collection.</span></span> <span data-ttu-id="1bb36-134"><xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A>Właściwość wskazuje, czy atrybut jest deklaracją przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="1bb36-134">The <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> property indicates whether an attribute is a namespace declaration.</span></span>

```csharp
XElement root = XElement.Parse(
@"<Root
    xmlns='http://www.adventure-works.com'
    xmlns:fc='www.fourthcoffee.com'
    AnAttribute='abc'/>");
foreach (XAttribute att in root.Attributes())
    Console.WriteLine("{0}  IsNamespaceDeclaration:{1}", att, att.IsNamespaceDeclaration);
```

```vb
Dim root As XElement = _
<Root
    xmlns='http://www.adventure-works.com'
    xmlns:fc='www.fourthcoffee.com'
    AnAttribute='abc'/>
For Each att As XAttribute In root.Attributes()
    Console.WriteLine("{0}  IsNamespaceDeclaration:{1}", att, _
                      att.IsNamespaceDeclaration)
Next
```

<span data-ttu-id="1bb36-135">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1bb36-135">This example produces the following output:</span></span>

```output
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True
AnAttribute="abc"  IsNamespaceDeclaration:False
```

## <a name="example-xpath-axis-methods-dont-return-the-child-text-nodes-of-xdocument"></a><span data-ttu-id="1bb36-136">Przykład: metody osi XPath nie zwracają podrzędnych węzłów tekstowych klasy XDocument</span><span class="sxs-lookup"><span data-stu-id="1bb36-136">Example: XPath axis methods don't return the child text nodes of XDocument</span></span>

<span data-ttu-id="1bb36-137">LINQ to XML zezwala na podrzędne węzły tekstowe <xref:System.Xml.Linq.XDocument> , tak długo, jak węzły tekstowe zawierają tylko biały znak.</span><span class="sxs-lookup"><span data-stu-id="1bb36-137">LINQ to XML allows for child text nodes of an <xref:System.Xml.Linq.XDocument>, as long as the text nodes contain only white space.</span></span> <span data-ttu-id="1bb36-138">Jednak model obiektów XPath nie zawiera białych znaków jako węzłów podrzędnych dokumentu, więc gdy przejdziesz do iteracji przez elementy podrzędne <xref:System.Xml.Linq.XDocument> za pomocą <xref:System.Xml.Linq.XContainer.Nodes%2A> osi, zostaną zwrócone węzły tekstu białych znaków.</span><span class="sxs-lookup"><span data-stu-id="1bb36-138">However, the XPath object model doesn't include white space as child nodes of a document, so when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the <xref:System.Xml.Linq.XContainer.Nodes%2A> axis, white space text nodes will be returned.</span></span> <span data-ttu-id="1bb36-139">Jednak podczas iteracji przez elementy podrzędne <xref:System.Xml.Linq.XDocument> za pomocą metody osi XPath, węzły tekstu odstępu nie zostaną zwrócone.</span><span class="sxs-lookup"><span data-stu-id="1bb36-139">However, when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the XPath axis methods, white space text nodes won't be returned.</span></span>

```csharp
// Create a document with some white space child nodes of the document.
XDocument root = XDocument.Parse(
@"<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<Root/>

<!--a comment-->
", LoadOptions.PreserveWhitespace);

// count the white space child nodes using LINQ to XML
Console.WriteLine(root.Nodes().OfType<XText>().Count());

// count the white space child nodes using XPathEvaluate
Console.WriteLine(((IEnumerable)root.XPathEvaluate("text()")).OfType<XText>().Count());
```

```vb
' Create a document with some white space child nodes of the document.
Dim root As XDocument = XDocument.Parse( _
"<?xml version='1.0' encoding='utf-8' standalone='yes'?>" & _
vbNewLine & "<Root/>" & vbNewLine & "<!--a comment-->" & vbNewLine, _
LoadOptions.PreserveWhitespace)

' Count the white space child nodes using LINQ to XML.
Console.WriteLine(root.Nodes().OfType(Of XText)().Count())

' Count the white space child nodes using XPathEvaluate.
Dim nodes As IEnumerable = CType(root.XPathEvaluate("text()"), IEnumerable)
Console.WriteLine(nodes.OfType(Of XText)().Count())
```

<span data-ttu-id="1bb36-140">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1bb36-140">This example produces the following output:</span></span>

```output
3
0
```

### <a name="the-xml-declaration-node-of-an-xdocument-is-a-property-not-a-child-node"></a><span data-ttu-id="1bb36-141">Węzeł deklaracji XML klasy XDocument jest właściwością, a nie węzłem podrzędnym.</span><span class="sxs-lookup"><span data-stu-id="1bb36-141">The XML declaration node of an XDocument is a property, not a child node</span></span>

<span data-ttu-id="1bb36-142">Gdy przejdziesz do iteracji między węzłami podrzędnymi <xref:System.Xml.Linq.XDocument> , nie zobaczysz obiektu deklaracji XML.</span><span class="sxs-lookup"><span data-stu-id="1bb36-142">When you iterate through the child nodes of an <xref:System.Xml.Linq.XDocument>, you won't see the XML declaration object.</span></span> <span data-ttu-id="1bb36-143">Jest to właściwość dokumentu, a nie jego węzła podrzędnego.</span><span class="sxs-lookup"><span data-stu-id="1bb36-143">It's a property of the document, not a child node of it.</span></span>

```csharp
XDocument doc = new XDocument(
    new XDeclaration("1.0", "utf-8", "yes"),
    new XElement("Root")
);
doc.Save("Temp.xml");
Console.WriteLine(File.ReadAllText("Temp.xml"));

// this shows that there is only one child node of the document
Console.WriteLine(doc.Nodes().Count());
```

```vb
Dim doc As XDocument = _
<?xml version='1.0' encoding='utf-8' standalone='yes'?>
<Root/>

doc.Save("Temp.xml")
Console.WriteLine(File.ReadAllText("Temp.xml"))

' This shows that there is only one child node of the document.
Console.WriteLine(doc.Nodes().Count())
```

<span data-ttu-id="1bb36-144">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1bb36-144">This example produces the following output:</span></span>

```output
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<Root />
1
```
