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
# <a name="programming-with-nodes-linq-to-xml"></a>Programowanie z węzłami (LINQ to XML)

LINQ to XML deweloperzy, którzy muszą pisać programy takie jak Edytor XML, system transformacji lub moduł zapisujący raport często potrzebują kodu, który działa na tym samym poziomie szczegółowości niż elementy i atrybuty. Często wymagają one pracy na poziomie węzła, manipulowania węzłami tekstowymi, instrukcjami przetwarzania i komentarzami przetwarzania. Ten artykuł zawiera informacje na temat programowania na poziomie węzła.

## <a name="example-the-parent-property-values-of-the-child-nodes-of-xdocument-are-set-to-null"></a>Przykład: `Parent` wartości właściwości węzłów podrzędnych klasy XDocument są ustawione na wartość `null`

<xref:System.Xml.Linq.XObject.Parent%2A>Właściwość zawiera element nadrzędny <xref:System.Xml.Linq.XElement> , a nie węzeł nadrzędny. Węzły podrzędne <xref:System.Xml.Linq.XDocument> nie mają elementu nadrzędnego <xref:System.Xml.Linq.XElement> . Ich element nadrzędny jest dokumentem, więc <xref:System.Xml.Linq.XObject.Parent%2A> Właściwość dla tych węzłów jest ustawiona na `null` .

Poniższy przykład ilustruje:

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

Ten przykład generuje następujące wyniki:

```output
True
True
```

## <a name="example-adding-text-may-or-may-not-create-a-new-text-node"></a>Przykład: dodanie tekstu może być niemożliwe lub nie można utworzyć nowego węzła tekstowego

W wielu modelach programowania XML sąsiadujące węzły tekstowe są zawsze scalane. Jest to czasami nazywane normalizacją węzłów tekstowych. LINQ to XML nie normalizuje węzłów tekstowych. Jeśli dodasz dwa węzły tekstowe do tego samego elementu, spowoduje to sąsiednie węzły tekstowe. Jednakże jeśli dodasz zawartość określoną jako ciąg, a nie jako <xref:System.Xml.Linq.XText> węzeł, LINQ to XML może scalić ciąg z sąsiednim węzłem tekstowym. Poniższy przykład ilustruje to.

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

 Ten przykład generuje następujące wyniki:

```output
1
1
2
```

## <a name="example-setting-a-text-node-value-to-the-empty-string-doesnt-delete-the-node"></a>Przykład: ustawienie wartości węzła tekstowego na pusty ciąg nie powoduje usunięcia węzła

W niektórych modelach programowania XML węzły tekstowe są gwarantowane, że nie zawierają pustego ciągu. Powodem jest to, że taki węzeł tekstowy nie ma wpływu na serializacji XML. Jednak z tego samego powodu, w którym jest możliwy sąsiednie węzły tekstowe, jeśli usuniesz tekst z węzła tekstowego przez ustawienie jego wartości na pusty ciąg, sam węzeł tekstu nie zostanie usunięty.

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

Ten przykład generuje następujące wyniki:

```output
>><<
```

## <a name="example-an-element-with-one-empty-text-node-is-serialized-differently-from-one-with-no-text-node"></a>Przykład: element z jednym pustym węzłem tekstowym jest serializowany inaczej niż jeden bez węzła tekstowego

Jeśli element zawiera tylko podrzędny węzeł tekstowy, który jest pusty, jest serializowany z składnią długiego tagu: `<Child></Child>` . Jeśli element nie zawiera żadnych węzłów podrzędnych, zostaje Zserializowany za pomocą składni krótkiej tagu: `<Child />` .

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

Ten przykład generuje następujące wyniki:

```xml
<Child1></Child1>
<Child2 />
```

## <a name="example-namespaces-are-attributes-in-the-linq-to-xml-tree"></a>Przykład: przestrzenie nazw są atrybutami w drzewie LINQ to XML

Mimo że deklaracje przestrzeni nazw mają identyczną składnię atrybutów, w niektórych interfejsach programowania, takich jak XSLT i XPath, deklaracje przestrzeni nazw nie są uważane za atrybuty. Jednak w LINQ to XML przestrzenie nazw są przechowywane jako <xref:System.Xml.Linq.XAttribute> obiekty w drzewie XML. W przypadku iteracji przez atrybuty elementu, który zawiera deklarację przestrzeni nazw, Deklaracja przestrzeni nazw jest jednym z elementów w zwróconej kolekcji. <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A>Właściwość wskazuje, czy atrybut jest deklaracją przestrzeni nazw.

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

Ten przykład generuje następujące wyniki:

```output
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True
AnAttribute="abc"  IsNamespaceDeclaration:False
```

## <a name="example-xpath-axis-methods-dont-return-the-child-text-nodes-of-xdocument"></a>Przykład: metody osi XPath nie zwracają podrzędnych węzłów tekstowych klasy XDocument

LINQ to XML zezwala na podrzędne węzły tekstowe <xref:System.Xml.Linq.XDocument> , tak długo, jak węzły tekstowe zawierają tylko biały znak. Jednak model obiektów XPath nie zawiera białych znaków jako węzłów podrzędnych dokumentu, więc gdy przejdziesz do iteracji przez elementy podrzędne <xref:System.Xml.Linq.XDocument> za pomocą <xref:System.Xml.Linq.XContainer.Nodes%2A> osi, zostaną zwrócone węzły tekstu białych znaków. Jednak podczas iteracji przez elementy podrzędne <xref:System.Xml.Linq.XDocument> za pomocą metody osi XPath, węzły tekstu odstępu nie zostaną zwrócone.

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

Ten przykład generuje następujące wyniki:

```output
3
0
```

### <a name="the-xml-declaration-node-of-an-xdocument-is-a-property-not-a-child-node"></a>Węzeł deklaracji XML klasy XDocument jest właściwością, a nie węzłem podrzędnym.

Gdy przejdziesz do iteracji między węzłami podrzędnymi <xref:System.Xml.Linq.XDocument> , nie zobaczysz obiektu deklaracji XML. Jest to właściwość dokumentu, a nie jego węzła podrzędnego.

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

Ten przykład generuje następujące wyniki:

```output
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<Root />
1
```
