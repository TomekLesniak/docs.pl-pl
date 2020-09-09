---
title: Jak znaleźć atrybuty elementów równorzędnych o określonej nazwie LINQ to XML
description: 'Dowiedz się, jak znaleźć każdy atrybut o określonej nazwie, który również należy do elementu równorzędnego węzła kontekstu. Pokazane są dwie metody: jedna używa XPathEvaluate, drugi używa zapytania LINQ to XML.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: c3133d64-523f-422d-8838-73d36b945ca0
ms.openlocfilehash: ca332f013fe8aea90b6203f5b602ab219362f5d3
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553858"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-linq-to-xml"></a>Jak znaleźć atrybuty elementów równorzędnych o określonej nazwie (LINQ to XML)

W tym artykule pokazano, jak używać <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> programu, aby znaleźć każdy atrybut o określonej nazwie, który również należy do elementu równorzędnego węzła kontekstu. W tym artykule pokazano również, jak za pomocą zapytania LINQ to XML wykonać tę samą czynność.

## <a name="example-find-all-sibling-elements-named-book-and-then-find-all-attributes-named-id"></a>Przykład: Znajdź wszystkie elementy równorzędne o nazwie `Book` , a następnie Znajdź wszystkie atrybuty o nazwie `id`

Ten przykład umożliwia znalezienie `Book` elementu w dokumencie XML [przykładowy plik XML: Books](sample-xml-file-books.md). Następnie znajduje wszystkie elementy równorzędne o nazwie `Book` i wszystkie atrybuty o nazwach `id` tych elementów. Wynik jest kolekcją atrybutów.

Wyrażenie XPath ma wartość `../Book/@id` .

```csharp
XDocument books = XDocument.Load("Books.xml");

XElement book =
    books
    .Root
    .Element("Book");

// LINQ to XML query
IEnumerable<XAttribute> list1 =
    from el in book.Parent.Elements("Book")
    select el.Attribute("id");

// XPath expression
IEnumerable<XAttribute> list2 =
  ((IEnumerable)book.XPathEvaluate("../Book/@id")).Cast<XAttribute>();

if (list1.Count() == list2.Count() &&
        list1.Intersect(list2).Count() == list1.Count())
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
foreach (XAttribute el in list1)
    Console.WriteLine(el);
```

```vb
Dim books as XDocument = XDocument.Load("Books.xml")
Dim book As XElement = books.Root.<Book>(0)

' LINQ to XML query
Dim list1 As IEnumerable(Of XAttribute) = _
    From el In book.Parent.<Book> _
    Select el.Attribute("id")

' XPath expression
Dim list2 As IEnumerable(Of XAttribute) = DirectCast(book. _
    XPathEvaluate("../Book/@id"), IEnumerable).Cast(Of XAttribute)()

If list1.Count() = list2.Count() And _
        (list1.Intersect(list2)).Count() = list1.Count() Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If

For Each el As XAttribute In list1
    Console.WriteLine(el)
Next
```

Ten przykład generuje następujące wyniki:

```output
Results are identical
id="bk101"
id="bk102"
```

## <a name="see-also"></a>Zobacz też

- [LINQ to XML dla użytkowników XPath (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)