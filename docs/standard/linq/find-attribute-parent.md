---
title: Jak znaleźć atrybut LINQ to XML nadrzędnego
description: 'Dowiedz się, jak nawigować do elementu i znajdować atrybut jego elementu nadrzędnego. Pokazane są dwie metody: jedna używa XPathEvaluate, drugi używa zapytania LINQ to XML.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 811766ecfdf2f080f29f21ae08981483f75a7e44
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553861"
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

## <a name="see-also"></a>Zobacz też

- [LINQ to XML dla użytkowników XPath (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
