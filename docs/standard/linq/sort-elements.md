---
title: Jak sortować elementy — LINQ to XML
description: Dowiedz się, jak napisać zapytanie, które sortuje jego wyniki.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 0e93add12e39c71c7312036917d42dd53450b712
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550070"
---
# <a name="how-to-sort-elements-linq-to-xml"></a><span data-ttu-id="39502-103">Jak sortować elementy (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="39502-103">How to sort elements (LINQ to XML)</span></span>

<span data-ttu-id="39502-104">Wyniki można sortować podczas wykonywania zapytania w formacie XML.</span><span class="sxs-lookup"><span data-stu-id="39502-104">You can sort your results when you query XML.</span></span> <span data-ttu-id="39502-105">Ten artykuł zawiera dwa przykłady: pierwszy sortuje wyniki dla kodu XML, który *nie znajduje* się w przestrzeni nazw, a drugi ma takie samo sortowanie, ale w przypadku kodu XML, który *znajduje się* w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="39502-105">This article provides two examples: the first sorts results for XML that *isn't* in a namespace, and the second does the same sort, but for XML that *is* in a namespace.</span></span>

## <a name="example-write-a-query-that-sorts-its-results"></a><span data-ttu-id="39502-106">Przykład: Napisz zapytanie, które sortuje jego wyniki</span><span class="sxs-lookup"><span data-stu-id="39502-106">Example: Write a query that sorts its results</span></span>

<span data-ttu-id="39502-107">Ten przykład pokazuje, jak napisać zapytanie, które sortuje jego wyniki.</span><span class="sxs-lookup"><span data-stu-id="39502-107">This example shows how to write a query that sorts its results.</span></span> <span data-ttu-id="39502-108">Używa [przykładowego pliku XML dokumentu XML: dane liczbowe](sample-xml-file-numerical-data.md).</span><span class="sxs-lookup"><span data-stu-id="39502-108">It uses XML document [Sample XML file: Numerical data](sample-xml-file-numerical-data.md).</span></span>

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

<span data-ttu-id="39502-109">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="39502-109">This example produces the following output:</span></span>

```output
0.99
4.95
6.99
24.50
29.00
66.00
89.99
```

## <a name="example-write-a-query-in-a-namespace-that-sorts-its-results"></a><span data-ttu-id="39502-110">Przykład: Napisz zapytanie w przestrzeni nazw, które sortuje jego wyniki</span><span class="sxs-lookup"><span data-stu-id="39502-110">Example: Write a query in a namespace that sorts its results</span></span>

<span data-ttu-id="39502-111">W poniższym przykładzie pokazano to samo zapytanie dla kodu XML, który znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="39502-111">The following example shows the same query for XML that's in a namespace.</span></span> <span data-ttu-id="39502-112">Używa [przykładowego pliku XML dokumentu XML: danych liczbowych w przestrzeni nazw](sample-xml-file-numerical-data-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="39502-112">It uses XML document [Sample XML file: Numerical data in a namespace](sample-xml-file-numerical-data-namespace.md).</span></span>

<span data-ttu-id="39502-113">Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).</span><span class="sxs-lookup"><span data-stu-id="39502-113">For more information, see [Namespaces overview](namespaces-overview.md).</span></span>

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

<span data-ttu-id="39502-114">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="39502-114">This example produces the following output:</span></span>

```output
0.99
4.95
6.99
24.50
29.00
66.00
89.99
```

## <a name="see-also"></a><span data-ttu-id="39502-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="39502-115">See also</span></span>

- [<span data-ttu-id="39502-116">Sortowanie danych (C#)</span><span class="sxs-lookup"><span data-stu-id="39502-116">Sorting Data (C#)</span></span>](../../csharp/programming-guide/concepts/linq/sorting-data.md)
- [<span data-ttu-id="39502-117">Sortowanie danych (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39502-117">Sorting Data (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/sorting-data.md)
- [<span data-ttu-id="39502-118">Zapytania podstawowe (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39502-118">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](./find-element-specific-attribute.md)
