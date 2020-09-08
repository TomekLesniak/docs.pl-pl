---
title: Jak pisać zapytania z skomplikowanym filtrowaniem LINQ to XML
description: Czasami chcesz pisać zapytania LINQ to XML ze złożonymi filtrami. Na przykład może być konieczne znalezienie wszystkich elementów, które mają element podrzędny o określonej nazwie i wartości.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
ms.openlocfilehash: c5e7f812364e7e96e3a4b8f5515d07a3524ec979
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553810"
---
# <a name="how-to-write-queries-with-complex-filtering-linq-to-xml"></a>Jak pisać zapytania z skomplikowanym filtrowaniem (LINQ to XML)

Czasami chcesz pisać zapytania LINQ to XML ze złożonymi filtrami. Na przykład może być konieczne znalezienie wszystkich elementów, które mają element podrzędny o określonej nazwie i wartości. Ten artykuł zawiera przykład tworzenia zapytania z skomplikowanym filtrowaniem.

## <a name="example-find-with-a-nested-query-in-the-where-clause"></a>Przykład: Znajdź z zagnieżdżonym zapytaniem w `Where` klauzuli

Ten przykład pokazuje, jak znaleźć wszystkie `PurchaseOrder` elementy, które mają:

- Element podrzędny, `Address` którego `Type` atrybut ma wartość "wysyłka".
- Element podrzędny `State` , który jest równy "NY".

Używa zapytania zagnieżdżonego w `Where` klauzuli i `Any` operator zwraca, `true` Jeśli kolekcja zawiera jakiekolwiek elementy. W przykładzie zastosowano [przykładowy plik XML dokumentu XML: wiele zamówień zakupu](sample-xml-file-multiple-purchase-orders.md).

Aby uzyskać więcej informacji na temat `Any` operatora, zobacz [Operacje kwantyfikatora (C#)](../../../docs/csharp/programming-guide/concepts/linq/quantifier-operations.md) i [Kwantyfikatory (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).

```csharp
XElement root = XElement.Load("PurchaseOrders.xml");
IEnumerable<XElement> purchaseOrders =
    from el in root.Elements("PurchaseOrder")
    where
        (from add in el.Elements("Address")
        where
            (string)add.Attribute("Type") == "Shipping" &&
            (string)add.Element("State") == "NY"
        select add)
        .Any()
    select el;
foreach (XElement el in purchaseOrders)
    Console.WriteLine((string)el.Attribute("PurchaseOrderNumber"));
```

```vb
Dim root As XElement = XElement.Load("PurchaseOrders.xml")
Dim purchaseOrders As IEnumerable(Of XElement) = _
    From el In root.<PurchaseOrder> _
    Where _
        (From add In el.<Address> _
        Where _
             add.@Type = "Shipping" And _
             add.<State>.Value = "NY" _
        Select add) _
    .Any() _
    Select el
For Each el As XElement In purchaseOrders
    Console.WriteLine(el.@PurchaseOrderNumber)
Next
```

Ten przykład generuje następujące wyniki:

```output
99505
```

## <a name="example-find-in-xml-thats-in-a-namespace"></a>Przykład: Znajdź w kodzie XML, który znajduje się w przestrzeni nazw

Poniższy przykład pokazuje takie samo zapytanie jak powyżej, ale dla kodu XML, który znajduje się w przestrzeni nazw. Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

Ten przykład używa [przykładowego pliku XML dokumentu XML: wiele zamówień zakupu w przestrzeni nazw](sample-xml-file-multiple-purchase-orders-namespace.md).

```csharp
XElement root = XElement.Load("PurchaseOrdersInNamespace.xml");
XNamespace aw = "http://www.adventure-works.com";
IEnumerable<XElement> purchaseOrders =
    from el in root.Elements(aw + "PurchaseOrder")
    where
        (from add in el.Elements(aw + "Address")
         where
             (string)add.Attribute(aw + "Type") == "Shipping" &&
             (string)add.Element(aw + "State") == "NY"
         select add)
        .Any()
    select el;
foreach (XElement el in purchaseOrders)
    Console.WriteLine((string)el.Attribute(aw + "PurchaseOrderNumber"));
```

```vb
Imports <xmlns:aw='http://www.adventure-works.com'>

Module Module1
    Sub Main()
        Dim root As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")
        Dim purchaseOrders As IEnumerable(Of XElement) = _
            From el In root.<aw:PurchaseOrder> _
            Where _
                (From add In el.<aw:Address> _
                Where _
                     add.@aw:Type = "Shipping" And _
                     add.<aw:State>.Value = "NY" _
                Select add) _
            .Any() _
            Select el
        For Each el As XElement In purchaseOrders
            Console.WriteLine(el.@aw:PurchaseOrderNumber)
        Next
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```output
99505
```

## <a name="see-also"></a>Zobacz też

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [Operacje projekcji (C#)](../../csharp/programming-guide/concepts/linq/projection-operations.md)
- [Operacje kwantyfikatora (C#)](../../csharp/programming-guide/concepts/linq/quantifier-operations.md)
- [Właściwości osi elementu podrzędnego XML (Visual Basic)](../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [Właściwości osi atrybutu XML (Visual Basic)](../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
- [Właściwość wartości XML (Visual Basic)](../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Operacje projekcji (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
- [Operacje kwantyfikatora (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)
