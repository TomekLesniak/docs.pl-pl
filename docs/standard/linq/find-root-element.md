---
title: Jak znaleźć element główny — LINQ to XML
description: Dowiedz się, jak używać XPath i LINQ to XML w językach C# i Visual Basic, aby znaleźć element główny dokumentu XML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: 16217960b84276bd3bb4c5cb6b38d7cb56d2b41e
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553161"
---
# <a name="how-to-find-the-root-element-linq-to-xml"></a>Jak znaleźć element główny (LINQ to XML)

W tym artykule przedstawiono przykład, w którym pokazano, jak używać XPath i LINQ to XML w języku C# i Visual Basic, aby znaleźć element główny dokumentu XML.

## <a name="example-find-the-root-element"></a>Przykład: Znajdź element główny

W tym przykładzie używamy zapytania LINQ to XML i XPath, aby znaleźć element główny w [przykładowym pliku XML dokumentu XML: wiele zamówień zakupu](sample-xml-file-multiple-purchase-orders.md). Wyrażenie XPath ma wartość `/PurchaseOrders` .

```csharp
XDocument po = XDocument.Load("PurchaseOrders.xml");

// LINQ to XML query
XElement el1 = po.Root;

// XPath expression
XElement el2 = po.XPathSelectElement("/PurchaseOrders");

if (el1 == el2)
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
Console.WriteLine(el1.Name);
```

```vb
Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")

' LINQ to XML query
Dim el1 As XElement = po.Root

' XPath expression
Dim el2 As XElement = po.XPathSelectElement("/PurchaseOrders")

If el1 Is el2 Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
Console.WriteLine(el1.Name)
```

Ten przykład generuje następujące wyniki:

```output
Results are identical
PurchaseOrders
```

## <a name="see-also"></a>Zobacz też

- [LINQ to XML dla użytkowników XPath (Visual Basic)](/../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
