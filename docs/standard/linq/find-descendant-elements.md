---
title: Jak znaleźć elementy zależne — LINQ to XML
description: W tym artykule przedstawiono sposób użycia kwerendy XPath i LINQ to XML w języku C# i Visual Basic, aby znaleźć wszystkie elementy zależne, które mają określoną nazwę.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: b318da39-bb8b-4c56-a019-e13b12b01831
ms.openlocfilehash: 36547c4ad39953e25bf7a8d5f69aa4a712e51982
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554233"
---
# <a name="how-to-find-descendant-elements-linq-to-xml"></a>Jak znaleźć elementy zależne (LINQ to XML)

W tym artykule przedstawiono sposób użycia kwerendy XPath i LINQ to XML w języku C# i Visual Basic, aby znaleźć wszystkie elementy zależne, które mają określoną nazwę.

## <a name="example-find-descendant-elements-that-have-a-specified-name"></a>Przykład znajdowania elementów podrzędnych, które mają określoną nazwę

 Ten przykład pokazuje, jak używać zapytań LINQ to XML i XPath do znajdowania wszystkich elementów potomnych o nazwie `Name` w dokumencie XML [przykładowy plik XML: wiele zamówień zakupu](sample-xml-file-multiple-purchase-orders.md). Wyrażenie XPath ma wartość `//Name` .

```csharp
XDocument po = XDocument.Load("PurchaseOrders.xml");

// LINQ to XML query
IEnumerable<XElement> list1 = po.Root.Descendants("Name");

// XPath expression
IEnumerable<XElement> list2 = po.XPathSelectElements("//Name");

if (list1.Count() == list2.Count() &&
        list1.Intersect(list2).Count() == list1.Count())
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
foreach (XElement el in list1)
    Console.WriteLine(el);
```

```vb
Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")

' LINQ to XML query
Dim list1 As IEnumerable(Of XElement) = po...<Name>

' XPath expression
Dim list2 As IEnumerable(Of XElement) = po.XPathSelectElements("//Name")

If (list1.Count() = list2.Count() And _
        list1.Intersect(list2).Count() = list1.Count()) Then
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
<Name>Tai Yee</Name>
<Name>Cristian Osorio</Name>
<Name>Cristian Osorio</Name>
<Name>Jessica Arnold</Name>
<Name>Jessica Arnold</Name>
```

## <a name="see-also"></a>Zobacz także

- [LINQ to XML dla użytkowników XPath (Visual Basic)](./comparison-xpath-linq-xml.md)
