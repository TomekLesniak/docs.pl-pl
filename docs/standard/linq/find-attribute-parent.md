---
title: Jak znaleźć atrybut LINQ to XML nadrzędnego
description: 'Dowiedz się, jak nawigować do elementu i znajdować atrybut jego elementu nadrzędnego. Pokazane są dwie metody: jedna używa XPathEvaluate, drugi używa zapytania LINQ to XML.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 6d5d1ce768f91aa6e32bf09668bad66f3c4f2334
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556361"
---
# <a name="how-to-find-an-attribute-of-the-parent-linq-to-xml"></a>Jak znaleźć atrybut elementu nadrzędnego (LINQ to XML)

W tym artykule pokazano, jak używać <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> programu do znajdowania atrybutu elementu nadrzędnego oraz jak używać zapytania LINQ to XML, aby wykonać to samo.

## <a name="example-find-the-author-element-and-then-find-the-id-attribute-of-its-parent"></a>Przykład: Znajdź `Author` element, a następnie Znajdź `id` atrybut jego elementu nadrzędnego

Ten przykład najpierw odnajduje `Author` element w dokumencie XML [przykładowy plik XML: Books](sample-xml-file-books.md), a następnie znajduje `id` atrybut jego elementu nadrzędnego.

Wyrażenie XPath ma wartość `../@id` .

```csharp
XDocument books = XDocument.Load("Books.xml");

XElement author =
    books
    .Root
    .Element("Book")
    .Element("Author");

// LINQ to XML query
XAttribute att1 =
    author
    .Parent
    .Attribute("id");

// XPath expression
XAttribute att2 = ((IEnumerable)author.XPathEvaluate("../@id")).Cast<XAttribute>().First();

if (att1 == att2)
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
Console.WriteLine(att1);
```

```vb
Dim books As XDocument = XDocument.Load("Books.xml")
Dim author As XElement = books.Root.<Book>.<Author>.FirstOrDefault()

' LINQ to XML query
Dim att1 As XAttribute = author.Parent.Attribute("id")

' XPath expression
Dim att2 As XAttribute = DirectCast(author.XPathEvaluate("../@id"),  _
    IEnumerable).Cast(Of XAttribute)().First()

If att1 Is att2 Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
Console.WriteLine(att1)
```

Ten przykład generuje następujące wyniki:

```output
Results are identical
id="bk101"
```

## <a name="see-also"></a>Zobacz także

- [LINQ to XML dla użytkowników XPath (Visual Basic)](./comparison-xpath-linq-xml.md)
