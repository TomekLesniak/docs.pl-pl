---
title: Jak znaleźć Unię dwóch ścieżek lokalizacji — LINQ to XML
description: 'Dowiedz się, jak znaleźć związek wyników dwóch ścieżek lokalizacji XPath. Pokazano dwie metody: jeden używa XPathSelectElements, drugi używa operatora standardowej kwerendy concat.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 069622d3-2b58-4919-8903-710a564c0788
ms.openlocfilehash: 13d1a22d933d789f28efa2d196fc0106986caa90
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555008"
---
# <a name="how-to-find-a-union-of-two-location-paths-linq-to-xml"></a>Jak znaleźć Unię dwóch ścieżek lokalizacji (LINQ to XML)

W tym artykule pokazano, jak używać programu <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> w celu znalezienia związku z wynikami dwóch ścieżek lokalizacji XPath oraz jak używać <xref:System.Linq.Enumerable.Concat%2A> standardowego operatora zapytań, aby wykonać tę samą czynność.

## <a name="example-find-all-category-and-price-elements-and-concatenate-them"></a>Przykład: Znajdź wszystko `Category` i `Price` elementy i połącz je

W tym przykładzie znaleziono wszystkie `Category` elementy i wszystkie `Price` elementy w [przykładowym pliku XML dokumentu XML: dane liczbowe](sample-xml-file-numerical-data.md)i łączy je w jedną kolekcję. Wyrażenie XPath ma wartość `//Category|//Price` .

> [!NOTE]
> Zapytanie LINQ to XML wywołuje, <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> Aby umieścić wyniki w kolejności dokumentu. Wyniki wyrażenia XPath również są w kolejności dokumentu.

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

Ten przykład generuje następujące wyniki:

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

## <a name="see-also"></a>Zobacz także

- [LINQ to XML dla użytkowników XPath (Visual Basic)](./comparison-xpath-linq-xml.md)
