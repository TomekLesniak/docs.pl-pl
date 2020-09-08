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
# <a name="how-to-sort-elements-linq-to-xml"></a>Jak sortować elementy (LINQ to XML)

Wyniki można sortować podczas wykonywania zapytania w formacie XML. Ten artykuł zawiera dwa przykłady: pierwszy sortuje wyniki dla kodu XML, który *nie znajduje* się w przestrzeni nazw, a drugi ma takie samo sortowanie, ale w przypadku kodu XML, który *znajduje się* w przestrzeni nazw.

## <a name="example-write-a-query-that-sorts-its-results"></a>Przykład: Napisz zapytanie, które sortuje jego wyniki

Ten przykład pokazuje, jak napisać zapytanie, które sortuje jego wyniki. Używa [przykładowego pliku XML dokumentu XML: dane liczbowe](sample-xml-file-numerical-data.md).

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

Ten przykład generuje następujące wyniki:

```output
0.99
4.95
6.99
24.50
29.00
66.00
89.99
```

## <a name="example-write-a-query-in-a-namespace-that-sorts-its-results"></a>Przykład: Napisz zapytanie w przestrzeni nazw, które sortuje jego wyniki

W poniższym przykładzie pokazano to samo zapytanie dla kodu XML, który znajduje się w przestrzeni nazw. Używa [przykładowego pliku XML dokumentu XML: danych liczbowych w przestrzeni nazw](sample-xml-file-numerical-data-namespace.md).

Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

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

Ten przykład generuje następujące wyniki:

```output
0.99
4.95
6.99
24.50
29.00
66.00
89.99
```

## <a name="see-also"></a>Zobacz też

- [Sortowanie danych (C#)](../../csharp/programming-guide/concepts/linq/sorting-data.md)
- [Sortowanie danych (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/sorting-data.md)
- [Zapytania podstawowe (LINQ to XML) (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
