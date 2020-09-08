---
title: Zapytania skompilowane statycznie — LINQ to XML
description: Dowiedz się, w jaki sposób zapytania LINQ to XML osiągają zalety wydajności w porównaniu do XmlDocument, które są kompilowane statycznie.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 3bf558fe-0705-479d-86d4-00188f5fcf9c
ms.openlocfilehash: 53dd47247eae8802dcf8187d0e82eb1c8bead9f9
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553416"
---
# <a name="statically-compiled-queries-linq-to-xml"></a>Zapytania skompilowane statycznie (LINQ to XML)

Jedną z najważniejszych zalet wydajności LINQ to XML, w porównaniu z <xref:System.Xml.XmlDocument> , jest to, że zapytania w LINQ to XML są kompilowane statycznie, podczas gdy zapytania XPath muszą być interpretowane w czasie wykonywania. Ta funkcja jest wbudowana w LINQ to XML, więc nie trzeba wykonywać dodatkowych czynności, aby korzystać z niej, ale warto zrozumieć rozróżnienie podczas wybierania dwóch technologii. W tym artykule opisano różnicę.

## <a name="statically-compiled-queries-vs-xpath"></a>Zapytania skompilowane statycznie a XPath

Poniższy przykład pokazuje, jak uzyskać elementy podrzędne o określonej nazwie i z atrybutem o określonej wartości. Równoważne wyrażenie XPath ma wartość `//Address[@Type='Shipping']` .

```csharp
XDocument po = XDocument.Load("PurchaseOrders.xml");

IEnumerable<XElement> list1 =
    from el in po.Descendants("Address")
    where (string)el.Attribute("Type") == "Shipping"
    select el;

foreach (XElement el in list1)
    Console.WriteLine(el);
```

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = From el In po.Descendants("Address")
            Where el.@Type = "Shipping"

For Each el In list1
    Console.WriteLine(el)
Next
```

Wyrażenie zapytania w tym przykładzie jest ponownie zapisywane przez kompilator do składni zapytania opartej na metodzie. Poniższy przykład, który został zapisany w składni zapytania opartej na metodzie, daje takie same wyniki jak poprzedni:

```csharp
XDocument po = XDocument.Load("PurchaseOrders.xml");

IEnumerable<XElement> list1 =
    po
    .Descendants("Address")
    .Where(el => (string)el.Attribute("Type") == "Shipping");

foreach (XElement el in list1)
    Console.WriteLine(el);
```

 ```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 As IEnumerable(Of XElement) = po.Descendants("Address").Where(Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

<xref:System.Linq.Enumerable.Where%2A>Metoda jest metodą rozszerzenia. Aby uzyskać więcej informacji, zobacz [metody rozszerzenia (Przewodnik programowania w języku C#)](../../csharp/programming-guide/classes-and-structs/extension-methods.md). Ponieważ <xref:System.Linq.Enumerable.Where%2A> jest to metoda rozszerzająca, zapytanie powyżej zostało skompilowane tak, jakby było zapisywane w następujący sposób:

```csharp
XDocument po = XDocument.Load("PurchaseOrders.xml");

IEnumerable<XElement> list1 =
    System.Linq.Enumerable.Where(
        po.Descendants("Address"),
        el => (string)el.Attribute("Type") == "Shipping");

foreach (XElement el in list1)
    Console.WriteLine(el);
```

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

Ten przykład daje dokładnie te same wyniki co dwa poprzednie przykłady. Ilustruje to fakt, że zapytania są efektywnie kompilowane na wywołania metod połączonych statycznie. W połączeniu z odroczoną semantyką wykonywania iteratorów, zwiększa wydajność. Aby uzyskać więcej informacji o odroczonej semantyki wykonywania iteratorów, zobacz [odroczone wykonywanie i obliczanie z opóźnieniem](deferred-execution-lazy-evaluation.md).

> [!NOTE]
> Te przykłady są reprezentatywne dla kodu, który kompilator może napisać. Rzeczywista implementacja może się nieco różnić od tych przykładów, ale wydajność będzie taka sama jak lub podobna do tych przykładów.

## <a name="executing-xpath-expressions-with-xmldocument"></a>Wykonywanie wyrażeń XPath przy użyciu elementu XmlDocument

Poniższy przykład używa <xref:System.Xml.XmlDocument> , aby wykonać te same wyniki co w poprzednich przykładach:

```csharp
XmlReader reader = XmlReader.Create("PurchaseOrders.xml");
XmlDocument doc = new XmlDocument();
doc.Load(reader);
XmlNodeList nl = doc.SelectNodes(".//Address[@Type='Shipping']");
foreach (XmlNode n in nl)
    Console.WriteLine(n.OuterXml);
reader.Close();
```

```vb
Dim reader = Xml.XmlReader.Create("PurchaseOrders.xml")
Dim doc As New Xml.XmlDocument()
doc.Load(reader)
Dim nl As Xml.XmlNodeList = doc.SelectNodes(".//Address[@Type='Shipping']")
For Each n As Xml.XmlNode In nl
    Console.WriteLine(n.OuterXml)
Next
reader.Close()
```

To zapytanie zwraca te same dane wyjściowe jak przykłady, które używają LINQ to XML; Jedyną różnicą jest to, że LINQ to XML wcięcia drukowanych danych XML, a <xref:System.Xml.XmlDocument> nie.

Jednak <xref:System.Xml.XmlDocument> podejście zwykle nie jest wykonywane, a LINQ to XML, ponieważ <xref:System.Xml.XmlNode.SelectNodes%2A> Metoda musi wykonać następujące czynności za każdym razem, gdy jest wywoływana:

- Przeanalizuj ciąg zawierający wyrażenie XPath, dzieląc ciąg na tokeny.
- Sprawdź poprawność tokenów, aby upewnić się, że wyrażenie XPath jest prawidłowe.
- Przekształć wyrażenie w wewnętrzne drzewo wyrażeń.
- Wykonaj iterację węzłów, odpowiednio wybierając węzły dla zestawu wyników na podstawie oceny wyrażenia.

Jest to znacznie więcej niż pracy wykonanej przez odpowiednie LINQ to XML zapytanie. Określona różnica wydajności różni się w zależności od różnych typów zapytań, ale w ogólnych zapytaniach LINQ to XML wykonuje mniej pracy i w związku z tym wykonuje lepsze, niż ocenianie wyrażeń XPath przy użyciu <xref:System.Xml.XmlDocument> .
