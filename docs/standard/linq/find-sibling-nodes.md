---
title: Jak znaleźć węzły elementów równorzędnych — LINQ to XML
description: 'Dowiedz się, jak znaleźć wszystkie elementy równorzędne węzła o określonej nazwie. Pokazane są dwie metody: jedna używa XPathSelectElements, drugi używa zapytania LINQ to XML.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: e2c73d10-a8ca-4e11-b5aa-d055de285874
ms.openlocfilehash: 3c764cec818cf788282bb616cc123e9be8d62c08
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553152"
---
# <a name="how-to-find-sibling-nodes-linq-to-xml"></a><span data-ttu-id="c6068-104">Jak znaleźć węzły elementów równorzędnych (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="c6068-104">How to find sibling nodes (LINQ to XML)</span></span>

<span data-ttu-id="c6068-105">W tym artykule pokazano, jak używać <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> programu do znajdowania wszystkich elementów równorzędnych węzła, które mają określoną nazwę, oraz sposobu używania zapytania LINQ to XML, aby wykonać tę samą czynność.</span><span class="sxs-lookup"><span data-stu-id="c6068-105">This article shows how to use <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to find all siblings of a node that have a specific name, and how to use LINQ to XML query to do the same thing.</span></span>

> [!NOTE]
> <span data-ttu-id="c6068-106">Utworzona kolekcja zawiera węzeł kontekstu, jeśli ma również określoną nazwę.</span><span class="sxs-lookup"><span data-stu-id="c6068-106">The resulting collection includes the context node if it also has the specific name.</span></span>

## <a name="example-find-an-element-named-book-and-all-sibling-elements-named-book"></a><span data-ttu-id="c6068-107">Przykład: Znajdź element o nazwie `Book` i wszystkie elementy równorzędne o nazwie `Book`</span><span class="sxs-lookup"><span data-stu-id="c6068-107">Example: Find an element named `Book`, and all sibling elements named `Book`</span></span>

<span data-ttu-id="c6068-108">Ten przykład najpierw odnajduje `Book` element w dokumencie XML [przykładowy plik XML: Books](sample-xml-file-books.md), a następnie znajduje wszystkie elementy równorzędne o nazwie `Book` .</span><span class="sxs-lookup"><span data-stu-id="c6068-108">This example first finds a `Book` element in XML document [Sample XML file: Books](sample-xml-file-books.md), and then finds all sibling elements named `Book`.</span></span> <span data-ttu-id="c6068-109">Kolekcja wyników zawiera węzeł kontekstu.</span><span class="sxs-lookup"><span data-stu-id="c6068-109">The resulting collection includes the context node.</span></span>

<span data-ttu-id="c6068-110">Wyrażenie XPath jest `../Book`</span><span class="sxs-lookup"><span data-stu-id="c6068-110">The XPath expression is `../Book`</span></span>

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

<span data-ttu-id="c6068-111">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="c6068-111">This example produces the following output:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c6068-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c6068-112">See also</span></span>

- [<span data-ttu-id="c6068-113">LINQ to XML dla użytkowników XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6068-113">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
