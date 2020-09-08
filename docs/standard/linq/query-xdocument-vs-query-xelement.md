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
# <a name="query-an-xdocument-vs-query-an-xelement-linq-to-xml"></a>Zapytanie `XDocument` a a Query a `XElement` (LINQ to XML)

Zapytanie, które należy napisać podczas ładowania dokumentu, <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> różni się od zapisu podczas ładowania za pośrednictwem programu <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> .

## <a name="comparison-of-xdocumentload-and-xelementload"></a>Porównanie `XDocument.Load` i `XElement.Load`

Podczas ładowania dokumentu XML do elementu <xref:System.Xml.Linq.XElement> za pośrednictwem <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> <xref:System.Xml.Linq.XElement> katalog główny drzewa XML zawiera element główny załadowanego dokumentu. Jednak podczas ładowania tego samego dokumentu XML do elementu <xref:System.Xml.Linq.XDocument> za pośrednictwem <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> katalog główny drzewa jest <xref:System.Xml.Linq.XDocument> węzłem, a głównym elementem załadowanego dokumentu jest jeden dozwolony <xref:System.Xml.Linq.XElement> węzeł podrzędny <xref:System.Xml.Linq.XDocument> . Osie LINQ to XML działają względem węzła głównego.

## <a name="example-load-an-xml-tree-using-xelementload-then-query-for-child-elements"></a>Przykład: Załaduj drzewo XML przy użyciu `XElement.Load` , a następnie wykonaj zapytanie dla elementów podrzędnych

Ten pierwszy przykład ładuje drzewo XML przy użyciu <xref:System.Xml.Linq.XElement.Load%2A> . Następnie wykonuje zapytanie dotyczące elementów podrzędnych katalogu głównego drzewa.

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

Ten przykład generuje następujące wyniki:

```output
Querying tree loaded with XElement.Load
----
<Child1>1</Child1>
<Child2>2</Child2>
<Child3>3</Child3>
```

## <a name="example-load-an-xml-tree-using-xdocumentload-then-query-for-child-elements"></a>Przykład: Załaduj drzewo XML przy użyciu `XDocument.Load` , a następnie wykonaj zapytanie dla elementów podrzędnych

Następny przykład jest taki sam jak powyżej, ale drzewo XML zostało załadowane do obiektu <xref:System.Xml.Linq.XDocument> , a nie <xref:System.Xml.Linq.XElement> .

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

Ten przykład generuje następujące wyniki:

```output
Querying tree loaded with XDocument.Load
----
<Root>
  <Child1>1</Child1>
  <Child2>2</Child2>
  <Child3>3</Child3>
</Root>
```

Zwróć uwagę, że to samo zapytanie zwróciło jeden `Root` węzeł zamiast trzech węzłów podrzędnych.

Jednym z metod postępowania z tym jest użycie <xref:System.Xml.Linq.XDocument.Root%2A> Właściwości przed uzyskaniem dostępu do metody osi w następujący sposób:

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

To zapytanie jest teraz wykonywane w taki sam sposób, jak zapytanie w drzewie w katalogu głównym <xref:System.Xml.Linq.XElement> .

Ten przykład generuje następujące wyniki:

```output
Querying tree loaded with XDocument.Load
----
<Child1>1</Child1>
<Child2>2</Child2>
<Child3>3</Child3>
```
