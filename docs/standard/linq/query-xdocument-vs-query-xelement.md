---
title: Wykonywanie zapytania dotyczącego metody XDocument a Query XElement-LINQ to XML
description: Zapisuj nieco inne zapytania dla dokumentów XML ładowanych przez XDocument. Load i XElement. Load.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 46221ff5-62ee-4de8-93ba-66465facb5c1
ms.openlocfilehash: 96d706bcc1871c9e420bafd984d08ca9616b5c18
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553708"
---
# <a name="query-an-xdocument-vs-query-an-xelement-linq-to-xml"></a><span data-ttu-id="0bd3f-103">Zapytanie `XDocument` a a Query a `XElement` (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="0bd3f-103">Query an `XDocument` vs. query an `XElement` (LINQ to XML)</span></span>

<span data-ttu-id="0bd3f-104">Zapytanie, które należy napisać podczas ładowania dokumentu, <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> różni się od zapisu podczas ładowania za pośrednictwem programu <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0bd3f-104">The query you write when you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> differs slighty from what you write when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span></span>

## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="0bd3f-105">Porównanie `XDocument.Load` i `XElement.Load`</span><span class="sxs-lookup"><span data-stu-id="0bd3f-105">Comparison of `XDocument.Load` and `XElement.Load`</span></span>

<span data-ttu-id="0bd3f-106">Podczas ładowania dokumentu XML do elementu <xref:System.Xml.Linq.XElement> za pośrednictwem <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> <xref:System.Xml.Linq.XElement> katalog główny drzewa XML zawiera element główny załadowanego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="0bd3f-106">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="0bd3f-107">Jednak podczas ładowania tego samego dokumentu XML do elementu <xref:System.Xml.Linq.XDocument> za pośrednictwem <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> katalog główny drzewa jest <xref:System.Xml.Linq.XDocument> węzłem, a głównym elementem załadowanego dokumentu jest jeden dozwolony <xref:System.Xml.Linq.XElement> węzeł podrzędny <xref:System.Xml.Linq.XDocument> .</span><span class="sxs-lookup"><span data-stu-id="0bd3f-107">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="0bd3f-108">Osie LINQ to XML działają względem węzła głównego.</span><span class="sxs-lookup"><span data-stu-id="0bd3f-108">The LINQ to XML axes operate relative to the root node.</span></span>

## <a name="example-load-an-xml-tree-using-xelementload-then-query-for-child-elements"></a><span data-ttu-id="0bd3f-109">Przykład: Załaduj drzewo XML przy użyciu `XElement.Load` , a następnie wykonaj zapytanie dla elementów podrzędnych</span><span class="sxs-lookup"><span data-stu-id="0bd3f-109">Example: Load an XML tree using `XElement.Load`, then query for child elements</span></span>

<span data-ttu-id="0bd3f-110">Ten pierwszy przykład ładuje drzewo XML przy użyciu <xref:System.Xml.Linq.XElement.Load%2A> .</span><span class="sxs-lookup"><span data-stu-id="0bd3f-110">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="0bd3f-111">Następnie wykonuje zapytanie dotyczące elementów podrzędnych katalogu głównego drzewa.</span><span class="sxs-lookup"><span data-stu-id="0bd3f-111">It then queries for the child elements of the root of the tree.</span></span>

```csharp
// Create a simple document and write it to a file
File.WriteAllText("Test.xml", @"<Root>
    <Child1>1</Child1>
    <Child2>2</Child2>
    <Child3>3</Child3>
</Root>");

Console.WriteLine("Querying tree loaded with XElement.Load");
Console.WriteLine("----");
XElement doc = XElement.Load("Test.xml");
IEnumerable<XElement> childList =
    from el in doc.Elements()
    select el;
foreach (XElement e in childList)
    Console.WriteLine(e);
```

```vb
' Create a simple document and  write it to a file
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _
    "    <Child1>1</Child1>" + Environment.NewLine + _
    "    <Child2>2</Child2>" + Environment.NewLine + _
    "    <Child3>3</Child3>" + Environment.NewLine + _
    "</Root>")

Console.WriteLine("Querying tree loaded with XElement.Load")
Console.WriteLine("----")
Dim doc As XElement = XElement.Load("Test.xml")
Dim childList As IEnumerable(Of XElement) = _
        From el In doc.Elements() _
        Select el
For Each e As XElement In childList
    Console.WriteLine(e)
Next
```

<span data-ttu-id="0bd3f-112">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="0bd3f-112">This example produces the following output:</span></span>

```output
Querying tree loaded with XElement.Load
----
<Child1>1</Child1>
<Child2>2</Child2>
<Child3>3</Child3>
```

## <a name="example-load-an-xml-tree-using-xdocumentload-then-query-for-child-elements"></a><span data-ttu-id="0bd3f-113">Przykład: Załaduj drzewo XML przy użyciu `XDocument.Load` , a następnie wykonaj zapytanie dla elementów podrzędnych</span><span class="sxs-lookup"><span data-stu-id="0bd3f-113">Example: Load an XML tree using `XDocument.Load`, then query for child elements</span></span>

<span data-ttu-id="0bd3f-114">Następny przykład jest taki sam jak powyżej, ale drzewo XML zostało załadowane do obiektu <xref:System.Xml.Linq.XDocument> , a nie <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="0bd3f-114">The next example does the same as the one above, but the XML tree has been loaded into an <xref:System.Xml.Linq.XDocument>, rather than an <xref:System.Xml.Linq.XElement>.</span></span>

```csharp
// Create a simple document and write it to a file
File.WriteAllText("Test.xml", @"<Root>
    <Child1>1</Child1>
    <Child2>2</Child2>
    <Child3>3</Child3>
</Root>");

Console.WriteLine("Querying tree loaded with XDocument.Load");
Console.WriteLine("----");
XDocument doc = XDocument.Load("Test.xml");
IEnumerable<XElement> childList =
    from el in doc.Elements()
    select el;
foreach (XElement e in childList)
    Console.WriteLine(e);
```

```vb
' Create a simple document and  write it to a file
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _
    "    <Child1>1</Child1>" + Environment.NewLine + _
    "    <Child2>2</Child2>" + Environment.NewLine + _
    "    <Child3>3</Child3>" + Environment.NewLine + _
    "</Root>")

Console.WriteLine("Querying tree loaded with XDocument.Load")
Console.WriteLine("----")
Dim doc As XDocument = XDocument.Load("Test.xml")
Dim childList As IEnumerable(Of XElement) = _
        From el In doc.Elements() _
        Select el
For Each e As XElement In childList
    Console.WriteLine(e)
Next
```

<span data-ttu-id="0bd3f-115">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="0bd3f-115">This example produces the following output:</span></span>

```output
Querying tree loaded with XDocument.Load
----
<Root>
  <Child1>1</Child1>
  <Child2>2</Child2>
  <Child3>3</Child3>
</Root>
```

<span data-ttu-id="0bd3f-116">Zwróć uwagę, że to samo zapytanie zwróciło jeden `Root` węzeł zamiast trzech węzłów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="0bd3f-116">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>

<span data-ttu-id="0bd3f-117">Jednym z metod postępowania z tym jest użycie <xref:System.Xml.Linq.XDocument.Root%2A> Właściwości przed uzyskaniem dostępu do metody osi w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="0bd3f-117">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>

```csharp
// Create a simple document and write it to a file
File.WriteAllText("Test.xml", @"<Root>
    <Child1>1</Child1>
    <Child2>2</Child2>
    <Child3>3</Child3>
</Root>");

Console.WriteLine("Querying tree loaded with XDocument.Load");
Console.WriteLine("----");
XDocument doc = XDocument.Load("Test.xml");
IEnumerable<XElement> childList =
    from el in doc.Root.Elements()
    select el;
foreach (XElement e in childList)
    Console.WriteLine(e);
```

```vb
' Create a simple document and  write it to a file
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _
    "    <Child1>1</Child1>" + Environment.NewLine + _
    "    <Child2>2</Child2>" + Environment.NewLine + _
    "    <Child3>3</Child3>" + Environment.NewLine + _
    "</Root>")

Console.WriteLine("Querying tree loaded with XDocument.Load")
Console.WriteLine("----")
Dim doc As XDocument = XDocument.Load("Test.xml")
Dim childList As IEnumerable(Of XElement) = _
        From el In doc.Root.Elements() _
        Select el
For Each e As XElement In childList
    Console.WriteLine(e)
Next
```

<span data-ttu-id="0bd3f-118">To zapytanie jest teraz wykonywane w taki sam sposób, jak zapytanie w drzewie w katalogu głównym <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="0bd3f-118">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span>

<span data-ttu-id="0bd3f-119">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="0bd3f-119">This example produces the following output:</span></span>

```output
Querying tree loaded with XDocument.Load
----
<Child1>1</Child1>
<Child2>2</Child2>
<Child3>3</Child3>
```
