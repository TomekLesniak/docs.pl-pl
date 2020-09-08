---
title: Jak znaleźć listę elementów podrzędnych — LINQ to XML
description: W tym artykule porównano oś elementów podrzędnych XPath z LINQ to XML osi XContainer. elementy.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 7c589dd8-f680-4cdb-9d6a-78d57e2555e8
ms.openlocfilehash: 84b820f3192a173130c485f3e7cdadf9499932f1
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553192"
---
# <a name="how-to-find-a-list-of-child-elements-linq-to-xml"></a>Jak znaleźć listę elementów podrzędnych (LINQ to XML)

W tym artykule porównano oś elementów podrzędnych XPath z <xref:System.Xml.Linq.XContainer.Elements%2A> osią LINQ to XML.

## <a name="example-find-all-child-elements-of-an-element"></a>Przykład: Znajdź wszystkie elementy podrzędne elementu

Ten przykład umożliwia znalezienie wszystkich elementów podrzędnych `Address` elementu w [przykładowym pliku XML dokumentu XML: wiele zamówień zakupu](sample-xml-file-multiple-purchase-orders.md).

Wyrażenie XPath: `./*`

```csharp
XDocument cpo = XDocument.Load("PurchaseOrders.xml");
XElement po = cpo.Root.Element("PurchaseOrder").Element("Address");

// LINQ to XML query
IEnumerable<XElement> list1 = po.Elements();

// XPath expression
IEnumerable<XElement> list2 = po.XPathSelectElements("./*");

if (list1.Count() == list2.Count() &&
        list1.Intersect(list2).Count() == list1.Count())
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
foreach (XElement el in list1)
    Console.WriteLine(el);
```

```vb
Dim cpo As XDocument = XDocument.Load("PurchaseOrders.xml")
Dim po As XElement = cpo.Root.<PurchaseOrder>.<Address>.FirstOrDefault

' LINQ to XML query
Dim list1 As IEnumerable(Of XElement) = po.Elements()

' XPath expression
Dim list2 As IEnumerable(Of XElement) = po.XPathSelectElements("./*")

If (list1.Count() = list2.Count()) AndAlso _
    (list1.Intersect(list2).Count() = list1.Count()) Then
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
<Name>Ellen Adams</Name>
<Street>123 Maple Street</Street>
<City>Mill Valley</City>
<State>CA</State>
<Zip>10999</Zip>
<Country>USA</Country>
```

## <a name="see-also"></a>Zobacz też

- [LINQ to XML dla użytkowników XPath (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
