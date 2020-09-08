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
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-linq-to-xml"></a><span data-ttu-id="8199d-104">Jak znaleźć atrybuty elementów równorzędnych o określonej nazwie (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="8199d-104">How to find attributes of siblings with a specific name (LINQ to XML)</span></span>

<span data-ttu-id="8199d-105">W tym artykule pokazano, jak używać <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> programu, aby znaleźć każdy atrybut o określonej nazwie, który również należy do elementu równorzędnego węzła kontekstu.</span><span class="sxs-lookup"><span data-stu-id="8199d-105">This article shows how to use <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> to find every attribute that has a specific name and that also belongs to a sibling of the context node.</span></span> <span data-ttu-id="8199d-106">W tym artykule pokazano również, jak za pomocą zapytania LINQ to XML wykonać tę samą czynność.</span><span class="sxs-lookup"><span data-stu-id="8199d-106">The article also shows how to use LINQ to XML query to do the same thing.</span></span>

## <a name="example-find-all-sibling-elements-named-book-and-then-find-all-attributes-named-id"></a><span data-ttu-id="8199d-107">Przykład: Znajdź wszystkie elementy równorzędne o nazwie `Book` , a następnie Znajdź wszystkie atrybuty o nazwie `id`</span><span class="sxs-lookup"><span data-stu-id="8199d-107">Example: Find all sibling elements named `Book`, and then find all attributes named `id`</span></span>

<span data-ttu-id="8199d-108">Ten przykład umożliwia znalezienie `Book` elementu w dokumencie XML [przykładowy plik XML: Books](sample-xml-file-books.md).</span><span class="sxs-lookup"><span data-stu-id="8199d-108">This example finds a `Book` element in XML document [Sample XML file: Books](sample-xml-file-books.md).</span></span> <span data-ttu-id="8199d-109">Następnie znajduje wszystkie elementy równorzędne o nazwie `Book` i wszystkie atrybuty o nazwach `id` tych elementów.</span><span class="sxs-lookup"><span data-stu-id="8199d-109">It then finds all sibling elements named `Book`, and all attributes named `id` of those elements.</span></span> <span data-ttu-id="8199d-110">Wynik jest kolekcją atrybutów.</span><span class="sxs-lookup"><span data-stu-id="8199d-110">The result is a collection of attributes.</span></span>

<span data-ttu-id="8199d-111">Wyrażenie XPath ma wartość `../Book/@id` .</span><span class="sxs-lookup"><span data-stu-id="8199d-111">The XPath expression is `../Book/@id`.</span></span>

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

<span data-ttu-id="8199d-112">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="8199d-112">This example produces the following output:</span></span>

```output
Results are identical
id="bk101"
id="bk102"
```

## <a name="see-also"></a><span data-ttu-id="8199d-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8199d-113">See also</span></span>

- [<span data-ttu-id="8199d-114">LINQ to XML dla użytkowników XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8199d-114">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
