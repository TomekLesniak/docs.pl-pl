---
title: Jak obliczyć wartości pośrednie — LINQ to XML
description: Oblicz wartości pośrednie do użycia podczas sortowania, filtrowania i wybierania.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: c37926b93e0dc11255fd27c312679f6286fa7e5d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558119"
---
# <a name="how-to-calculate-intermediate-values-linq-to-xml"></a>Jak obliczyć wartości pośrednie (LINQ to XML)

W tym artykule przedstawiono sposób obliczania wartości pośrednich do użycia podczas sortowania, filtrowania i wybierania w języku C# i Visual Basic.

## <a name="example-use-the-let-clause-to-calculate-based-on-element-data"></a>Przykład: Użyj `let` klauzuli, aby obliczyć na podstawie danych elementu

W poniższym przykładzie zastosowano `let` klauzulę do obliczania iloczynów wartości liczbowych z elementów. Używa [przykładowego pliku XML dokumentu XML: dane liczbowe](sample-xml-file-numerical-data.md).

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

Ten przykład generuje następujące wyniki:

```output
55.92
73.50
89.99
198.00
435.00
```

## <a name="example-calculate-from-xml-thats-in-a-namespace"></a>Przykład: Oblicz z pliku XML, który znajduje się w przestrzeni nazw

Poniższy przykład pokazuje to samo zapytanie jak wcześniej, ale dla kodu XML, który znajduje się w przestrzeni nazw. Używa [przykładowego pliku XML dokumentu XML: danych liczbowych w przestrzeni nazw](sample-xml-file-numerical-data-namespace.md).

Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

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

Ten przykład generuje następujące wyniki:

```output
55.92
73.50
89.99
198.00
435.00
```

## <a name="see-also"></a>Zobacz także

- [Zapytania podstawowe (LINQ to XML) (Visual Basic)](./find-element-specific-attribute.md)
