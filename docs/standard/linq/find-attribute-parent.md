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
# <a name="how-to-find-an-attribute-of-the-parent-linq-to-xml"></a><span data-ttu-id="c67e9-104">Jak znaleźć atrybut elementu nadrzędnego (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="c67e9-104">How to find an attribute of the parent (LINQ to XML)</span></span>

<span data-ttu-id="c67e9-105">W tym artykule pokazano, jak używać <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> programu do znajdowania atrybutu elementu nadrzędnego oraz jak używać zapytania LINQ to XML, aby wykonać to samo.</span><span class="sxs-lookup"><span data-stu-id="c67e9-105">This article shows how to use <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> to find an attribute of a parent element, and how to use LINQ to XML query to do the same thing.</span></span>

## <a name="example-find-the-author-element-and-then-find-the-id-attribute-of-its-parent"></a><span data-ttu-id="c67e9-106">Przykład: Znajdź `Author` element, a następnie Znajdź `id` atrybut jego elementu nadrzędnego</span><span class="sxs-lookup"><span data-stu-id="c67e9-106">Example: Find the `Author` element, and then find the `id` attribute of its parent</span></span>

<span data-ttu-id="c67e9-107">Ten przykład najpierw odnajduje `Author` element w dokumencie XML [przykładowy plik XML: Books](sample-xml-file-books.md), a następnie znajduje `id` atrybut jego elementu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="c67e9-107">This example first finds an `Author` element in XML document [Sample XML file: Books](sample-xml-file-books.md), and then finds the `id` attribute of its parent element.</span></span>

<span data-ttu-id="c67e9-108">Wyrażenie XPath ma wartość `../@id` .</span><span class="sxs-lookup"><span data-stu-id="c67e9-108">The XPath expression is `../@id`.</span></span>

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

<span data-ttu-id="c67e9-109">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="c67e9-109">This example produces the following output:</span></span>

```output
Results are identical
id="bk101"
```

## <a name="see-also"></a><span data-ttu-id="c67e9-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c67e9-110">See also</span></span>

- [<span data-ttu-id="c67e9-111">LINQ to XML dla użytkowników XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c67e9-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](./comparison-xpath-linq-xml.md)
