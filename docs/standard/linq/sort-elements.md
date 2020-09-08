---
title: Jak sortować elementy — LINQ to XML
description: Dowiedz się, jak napisać zapytanie, które sortuje jego wyniki.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: c2d7915aacf0c41e99581fa8b5cc397bcaf5c612
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553419"
---
# <a name="how-to-sort-elements-linq-to-xml"></a><span data-ttu-id="c877d-103">Jak sortować elementy (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="c877d-103">How to sort elements (LINQ to XML)</span></span>

<span data-ttu-id="c877d-104">Wyniki można sortować podczas wykonywania zapytania w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="c877d-104">You can sort your results when you query XML.</span></span> <span data-ttu-id="c877d-105">Ten artykuł zawiera dwa przykłady: pierwszy sortuje wyniki dla kodu XML, który *nie znajduje* się w przestrzeni nazw, a drugi ma takie samo sortowanie, ale w przypadku kodu XML, który *znajduje się* w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="c877d-105">This article provides two examples: the first sorts results for XML that *isn't* in a namespace, and the second does the same sort, but for XML that *is* in a namespace.</span></span>

## <a name="example-write-a-query-that-sorts-its-results"></a><span data-ttu-id="c877d-106">Przykład: Napisz zapytanie, które sortuje jego wyniki</span><span class="sxs-lookup"><span data-stu-id="c877d-106">Example: Write a query that sorts its results</span></span>

<span data-ttu-id="c877d-107">Ten przykład pokazuje, jak napisać zapytanie, które sortuje jego wyniki.</span><span class="sxs-lookup"><span data-stu-id="c877d-107">This example shows how to write a query that sorts its results.</span></span> <span data-ttu-id="c877d-108">Używa [przykładowego pliku XML dokumentu XML: dane liczbowe](sample-xml-file-numerical-data.md).</span><span class="sxs-lookup"><span data-stu-id="c877d-108">It uses XML document [Sample XML file: Numerical data](sample-xml-file-numerical-data.md).</span></span>

```csharp
XElement root = XElement.Load("Data.xml");
IEnumerable<decimal> prices =
    from el in root.Elements("Data")
    let price = (decimal)el.Element("Price")
    orderby price
    select price;
foreach (decimal el in prices)
    Console.WriteLine(el);
```

```vb
Dim root As XElement = XElement.Load("Data.xml")
Dim prices As IEnumerable(Of Decimal) = _
    From el In root.<Data> _
    Let price = Convert.ToDecimal(el.<Price>.Value) _
    Order By (price) _
    Select price
For Each el As Decimal In prices
    Console.WriteLine(el)
Next
```

<span data-ttu-id="c877d-109">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="c877d-109">This example produces the following output:</span></span>

```output
0.99
4.95
6.99
24.50
29.00
66.00
89.99
```

## <a name="example-write-a-query-in-a-namespace-that-sorts-its-results"></a><span data-ttu-id="c877d-110">Przykład: Napisz zapytanie w przestrzeni nazw, które sortuje jego wyniki</span><span class="sxs-lookup"><span data-stu-id="c877d-110">Example: Write a query in a namespace that sorts its results</span></span>

<span data-ttu-id="c877d-111">W poniższym przykładzie pokazano to samo zapytanie dla kodu XML, który znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="c877d-111">The following example shows the same query for XML that's in a namespace.</span></span> <span data-ttu-id="c877d-112">Używa [przykładowego pliku XML dokumentu XML: danych liczbowych w przestrzeni nazw](sample-xml-file-numerical-data-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="c877d-112">It uses XML document [Sample XML file: Numerical data in a namespace](sample-xml-file-numerical-data-namespace.md).</span></span>

<span data-ttu-id="c877d-113">Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c877d-113">For more information, see [Namespaces overview](namespaces-overview.md).</span></span>

```csharp
XElement root = XElement.Load("DataInNamespace.xml");
XNamespace aw = "http://www.adatum.com";
IEnumerable<decimal> prices =
    from el in root.Elements(aw + "Data")
    let price = (decimal)el.Element(aw + "Price")
    orderby price
    select price;
foreach (decimal el in prices)
    Console.WriteLine(el);
```

```vb
Imports <xmlns='http://www.adatum.com'>

Module Module1
    Sub Main()
        Dim root As XElement = XElement.Load("DataInNamespace.xml")
        Dim prices As IEnumerable(Of Decimal) = _
            From el In root.<Data> _
            Let price = Convert.ToDecimal(el.<Price>.Value) _
            Order By (price) _
            Select price
        For Each el As Decimal In prices
            Console.WriteLine(el)
        Next
    End Sub
End Module
```

<span data-ttu-id="c877d-114">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="c877d-114">This example produces the following output:</span></span>

```output
0.99
4.95
6.99
24.50
29.00
66.00
89.99
```

## <a name="see-also"></a><span data-ttu-id="c877d-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c877d-115">See also</span></span>

- [<span data-ttu-id="c877d-116">Sortowanie danych (C#)</span><span class="sxs-lookup"><span data-stu-id="c877d-116">Sorting Data (C#)</span></span>](../../csharp/programming-guide/concepts/linq/sorting-data.md)
- [<span data-ttu-id="c877d-117">Sortowanie danych (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c877d-117">Sorting Data (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/sorting-data.md)
- [<span data-ttu-id="c877d-118">Zapytania podstawowe (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c877d-118">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
