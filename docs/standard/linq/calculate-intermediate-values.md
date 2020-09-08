---
title: Jak obliczyć wartości pośrednie — LINQ to XML
description: Oblicz wartości pośrednie do użycia podczas sortowania, filtrowania i wybierania.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: aa5b83e9bf359481773db673fd3de9c4dcff6af2
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553026"
---
# <a name="how-to-calculate-intermediate-values-linq-to-xml"></a><span data-ttu-id="2d2f4-103">Jak obliczyć wartości pośrednie (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="2d2f4-103">How to calculate intermediate values (LINQ to XML)</span></span>

<span data-ttu-id="2d2f4-104">W tym artykule przedstawiono sposób obliczania wartości pośrednich do użycia podczas sortowania, filtrowania i wybierania w języku C# i Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2d2f4-104">This article shows how to calculate intermediate values for use in sorting, filtering, and selecting in C# and Visual Basic.</span></span>

## <a name="example-use-the-let-clause-to-calculate-based-on-element-data"></a><span data-ttu-id="2d2f4-105">Przykład: Użyj `let` klauzuli, aby obliczyć na podstawie danych elementu</span><span class="sxs-lookup"><span data-stu-id="2d2f4-105">Example: Use the `let` clause to calculate based on element data</span></span>

<span data-ttu-id="2d2f4-106">W poniższym przykładzie zastosowano `let` klauzulę do obliczania iloczynów wartości liczbowych z elementów.</span><span class="sxs-lookup"><span data-stu-id="2d2f4-106">The following example uses the `let` clause to calculate products of numerical values from elements.</span></span> <span data-ttu-id="2d2f4-107">Używa [przykładowego pliku XML dokumentu XML: dane liczbowe](sample-xml-file-numerical-data.md).</span><span class="sxs-lookup"><span data-stu-id="2d2f4-107">It uses XML document [Sample XML file: Numerical data](sample-xml-file-numerical-data.md).</span></span>

```csharp
XElement root = XElement.Load("Data.xml");
IEnumerable<decimal> extensions =
    from el in root.Elements("Data")
    let extension = (decimal)el.Element("Quantity") * (decimal)el.Element("Price")
    where extension >= 25
    orderby extension
    select extension;
foreach (decimal ex in extensions)
    Console.WriteLine(ex);
```

```vb
Dim root As XElement = XElement.Load("Data.xml")
Dim extensions As IEnumerable(Of Decimal) = _
    From el In root.<Data> _
    Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _
    Where extension > 25 _
    Order By extension _
    Select extension
For Each ex As Decimal In extensions
    Console.WriteLine(ex)
Next
```

<span data-ttu-id="2d2f4-108">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="2d2f4-108">This example produces the following output:</span></span>

```output
55.92
73.50
89.99
198.00
435.00
```

## <a name="example-calculate-from-xml-thats-in-a-namespace"></a><span data-ttu-id="2d2f4-109">Przykład: Oblicz z pliku XML, który znajduje się w przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="2d2f4-109">Example: Calculate from XML that's in a namespace</span></span>

<span data-ttu-id="2d2f4-110">Poniższy przykład pokazuje to samo zapytanie jak wcześniej, ale dla kodu XML, który znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="2d2f4-110">The following example shows the same query as before, but for XML that's in a namespace.</span></span> <span data-ttu-id="2d2f4-111">Używa [przykładowego pliku XML dokumentu XML: danych liczbowych w przestrzeni nazw](sample-xml-file-numerical-data-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="2d2f4-111">It uses the XML document [Sample XML file: Numerical data in a namespace](sample-xml-file-numerical-data-namespace.md).</span></span>

<span data-ttu-id="2d2f4-112">Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2d2f4-112">For more information, see [Namespaces overview](namespaces-overview.md).</span></span>

```csharp
XElement root = XElement.Load("DataInNamespace.xml");
XNamespace ad = "http://www.adatum.com";
IEnumerable<decimal> extensions =
    from el in root.Elements(ad + "Data")
    let extension = (decimal)el.Element(ad + "Quantity") * (decimal)el.Element(ad + "Price")
    where extension >= 25
    orderby extension
    select extension;
foreach (decimal ex in extensions)
    Console.WriteLine(ex);
```

```vb
Imports <xmlns="http://www.adatum.com">

Module Module1
    Sub Main()
        Dim root As XElement = XElement.Load("DataInNamespace.xml")
        Dim extensions As IEnumerable(Of Decimal) = _
            From el In root.<Data> _
            Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _
            Where extension > 25 _
            Order By extension _
            Select extension
        For Each ex As Decimal In extensions
            Console.WriteLine(ex)
        Next
    End Sub
End Module
```

<span data-ttu-id="2d2f4-113">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="2d2f4-113">This example produces the following output:</span></span>

```output
55.92
73.50
89.99
198.00
435.00
```

## <a name="see-also"></a><span data-ttu-id="2d2f4-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2d2f4-114">See also</span></span>

- [<span data-ttu-id="2d2f4-115">Zapytania podstawowe (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d2f4-115">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
