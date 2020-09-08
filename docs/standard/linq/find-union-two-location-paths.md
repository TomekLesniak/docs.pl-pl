---
title: Jak znaleźć Unię dwóch ścieżek lokalizacji — LINQ to XML
description: 'Dowiedz się, jak znaleźć związek wyników dwóch ścieżek lokalizacji XPath. Pokazano dwie metody: jeden używa XPathSelectElements, drugi używa operatora standardowej kwerendy concat.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 069622d3-2b58-4919-8903-710a564c0788
ms.openlocfilehash: ba2a1eef73a586074c75a7fec84c912acb8b25e9
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553101"
---
# <a name="how-to-find-a-union-of-two-location-paths-linq-to-xml"></a><span data-ttu-id="67c85-104">Jak znaleźć Unię dwóch ścieżek lokalizacji (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="67c85-104">How to find a union of two location paths (LINQ to XML)</span></span>

<span data-ttu-id="67c85-105">W tym artykule pokazano, jak używać programu <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> w celu znalezienia związku z wynikami dwóch ścieżek lokalizacji XPath oraz jak używać <xref:System.Linq.Enumerable.Concat%2A> standardowego operatora zapytań, aby wykonać tę samą czynność.</span><span class="sxs-lookup"><span data-stu-id="67c85-105">This article shows how to use <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to find the union of the results of two XPath location paths, and how to use the <xref:System.Linq.Enumerable.Concat%2A> standard query operator to do the same thing.</span></span>

## <a name="example-find-all-category-and-price-elements-and-concatenate-them"></a><span data-ttu-id="67c85-106">Przykład: Znajdź wszystko `Category` i `Price` elementy i połącz je</span><span class="sxs-lookup"><span data-stu-id="67c85-106">Example: Find all `Category` and `Price` elements and concatenate them</span></span>

<span data-ttu-id="67c85-107">W tym przykładzie znaleziono wszystkie `Category` elementy i wszystkie `Price` elementy w [przykładowym pliku XML dokumentu XML: dane liczbowe](sample-xml-file-numerical-data.md)i łączy je w jedną kolekcję.</span><span class="sxs-lookup"><span data-stu-id="67c85-107">This example finds all of the `Category` elements and all of the `Price` elements in XML document [Sample XML file: Numerical data](sample-xml-file-numerical-data.md), and concatenates them into a single collection.</span></span> <span data-ttu-id="67c85-108">Wyrażenie XPath ma wartość `//Category|//Price` .</span><span class="sxs-lookup"><span data-stu-id="67c85-108">The XPath expression is `//Category|//Price`.</span></span>

> [!NOTE]
> <span data-ttu-id="67c85-109">Zapytanie LINQ to XML wywołuje, <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> Aby umieścić wyniki w kolejności dokumentu.</span><span class="sxs-lookup"><span data-stu-id="67c85-109">The LINQ to XML query calls <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> to put the results in document order.</span></span> <span data-ttu-id="67c85-110">Wyniki wyrażenia XPath również są w kolejności dokumentu.</span><span class="sxs-lookup"><span data-stu-id="67c85-110">The XPath expression results are also in document order.</span></span>

```csharp
XDocument data = XDocument.Load("Data.xml");

// LINQ to XML query
IEnumerable<XElement> list1 =
    data
    .Descendants("Category")
    .Concat(
        data
        .Descendants("Price")
    )
    .InDocumentOrder();

// XPath expression
IEnumerable<XElement> list2 = data.XPathSelectElements("//Category|//Price");

if (list1.Count() == list2.Count() &&
        list1.Intersect(list2).Count() == list1.Count())
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
foreach (XElement el in list1)
    Console.WriteLine(el);
```

```vb
Dim data As XDocument = XDocument.Load("Data.xml")

' LINQ to XML query
Dim list1 As IEnumerable(Of XElement) = _
    data...<Category>.Concat(data...<Price>).InDocumentOrder()

' XPath expression
Dim list2 As IEnumerable(Of XElement) = _
    data.XPathSelectElements("//Category|//Price")

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

<span data-ttu-id="67c85-111">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="67c85-111">This example produces the following output:</span></span>

```output
Results are identical
<Category>A</Category>
<Price>24.50</Price>
<Category>B</Category>
<Price>89.99</Price>
<Category>A</Category>
<Price>4.95</Price>
<Category>A</Category>
<Price>66.00</Price>
<Category>B</Category>
<Price>.99</Price>
<Category>A</Category>
<Price>29.00</Price>
<Category>B</Category>
<Price>6.99</Price>
```

## <a name="see-also"></a><span data-ttu-id="67c85-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="67c85-112">See also</span></span>

- [<span data-ttu-id="67c85-113">LINQ to XML dla użytkowników XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67c85-113">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
