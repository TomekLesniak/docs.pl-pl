---
title: Jak znaleźć węzły elementów równorzędnych — LINQ to XML
description: 'Dowiedz się, jak znaleźć wszystkie elementy równorzędne węzła o określonej nazwie. Pokazane są dwie metody: jedna używa XPathSelectElements, drugi używa zapytania LINQ to XML.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: e2c73d10-a8ca-4e11-b5aa-d055de285874
ms.openlocfilehash: 56833ef3758a6d8af1eb6f0a103b85ad967c9aad
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555912"
---
# <a name="how-to-find-sibling-nodes-linq-to-xml"></a>Jak znaleźć węzły elementów równorzędnych (LINQ to XML)

W tym artykule pokazano, jak używać <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> programu do znajdowania wszystkich elementów równorzędnych węzła, które mają określoną nazwę, oraz sposobu używania zapytania LINQ to XML, aby wykonać tę samą czynność.

> [!NOTE]
> Utworzona kolekcja zawiera węzeł kontekstu, jeśli ma również określoną nazwę.

## <a name="example-find-an-element-named-book-and-all-sibling-elements-named-book"></a>Przykład: Znajdź element o nazwie `Book` i wszystkie elementy równorzędne o nazwie `Book`

Ten przykład najpierw odnajduje `Book` element w dokumencie XML [przykładowy plik XML: Books](sample-xml-file-books.md), a następnie znajduje wszystkie elementy równorzędne o nazwie `Book` . Kolekcja wyników zawiera węzeł kontekstu.

Wyrażenie XPath jest `../Book`

```csharp
XDocument books = XDocument.Load("Books.xml");

XElement book =
    books
    .Root
    .Elements("Book")
    .Skip(1)
    .First();

// LINQ to XML query
IEnumerable<XElement> list1 =
    book
    .Parent
    .Elements("Book");

// XPath expression
IEnumerable<XElement> list2 = book.XPathSelectElements("../Book");

if (list1.Count() == list2.Count() &&
        list1.Intersect(list2).Count() == list1.Count())
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
foreach (XElement el in list1)
    Console.WriteLine(el);
```

```vb
Dim books As XDocument = XDocument.Load("Books.xml")
Dim book As XElement = books.Root.<Book>.Skip(1).First()

' LINQ to XML query
Dim list1 As IEnumerable(Of XElement) = book.Parent.<Book>

' XPath expression
Dim list2 As IEnumerable(Of XElement) = book.XPathSelectElements("../Book")

If list1.Count() = list2.Count() And _
        list1.Intersect(list2).Count() = list1.Count() Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
For Each el As XElement In list1
    Console.WriteLine(el)
Next
```

Ten przykład generuje następujące wyniki:

```output
Results are identical
<Book id="bk101">
  <Author>Garghentini, Davide</Author>
  <Title>XML Developer's Guide</Title>
  <Genre>Computer</Genre>
  <Price>44.95</Price>
  <PublishDate>2000-10-01</PublishDate>
  <Description>An in-depth look at creating applications
      with XML.</Description>
</Book>
<Book id="bk102">
  <Author>Garcia, Debra</Author>
  <Title>Midnight Rain</Title>
  <Genre>Fantasy</Genre>
  <Price>5.95</Price>
  <PublishDate>2000-12-16</PublishDate>
  <Description>A former architect battles corporate zombies,
      an evil sorceress, and her own childhood to become queen
      of the world.</Description>
</Book>
```

## <a name="see-also"></a>Zobacz także

- [LINQ to XML dla użytkowników XPath (Visual Basic)](./comparison-xpath-linq-xml.md)
