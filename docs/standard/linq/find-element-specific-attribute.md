---
title: Jak znaleźć element z określonym atrybutem — LINQ to XML
description: Dowiedz się, jak znaleźć element, którego atrybut ma określoną wartość.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: b92591aa-3cfb-490e-99f6-da8de335e362
ms.openlocfilehash: 4c74de90a348d81ac87c98bf6ee27f3c78f34e83
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552870"
---
# <a name="how-to-find-an-element-with-a-specific-attribute-linq-to-xml"></a>Jak znaleźć element z określonym atrybutem (LINQ to XML)

W tym artykule przedstawiono przykłady znajdowania elementu, którego atrybut ma określoną wartość.

## <a name="example-find-an-element-whose-attribute-has-a-specific-value"></a>Przykład: Znajdź element, którego atrybut ma określoną wartość

Poniższy przykład pokazuje, jak znaleźć `Address` element, który ma `Type` atrybut o wartości "rozliczenia". W przykładzie zastosowano [przykładowy plik XML dokumentu XML: typowe zamówienie zakupu](sample-xml-file-typical-purchase-order.md).

```csharp
XElement root = XElement.Load("PurchaseOrder.xml");
IEnumerable<XElement> address =
    from el in root.Elements("Address")
    where (string)el.Attribute("Type") == "Billing"
    select el;
foreach (XElement el in address)
    Console.WriteLine(el);
```

```vb
Dim root As XElement = XElement.Load("PurchaseOrder.xml")
Dim address As IEnumerable(Of XElement) = _
    From el In root.<Address> _
    Where el.@Type = "Billing" _
    Select el
For Each el As XElement In address
    Console.WriteLine(el)
Next
```

Ten przykład generuje następujące wyniki:

```xml
<Address Type="Billing">
  <Name>Tai Yee</Name>
  <Street>8 Oak Avenue</Street>
  <City>Old Town</City>
  <State>PA</State>
  <Zip>95819</Zip>
  <Country>USA</Country>
</Address>
```

## <a name="example-find-an-element-in-xml-thats-in-a-namespace"></a>Przykład: Znajdź element w kodzie XML, który znajduje się w przestrzeni nazw

W poniższym przykładzie pokazano to samo zapytanie, ale w przypadku kodu XML, który znajduje się w przestrzeni nazw. Używa [przykładowego pliku XML dokumentu XML: typowe zamówienie zakupu w przestrzeni nazw](sample-xml-file-typical-purchase-order-namespace.md).

Aby uzyskać więcej informacji na temat przestrzeni nazw, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

```csharp
XElement root = XElement.Load("PurchaseOrderInNamespace.xml");
XNamespace aw = "http://www.adventure-works.com";
IEnumerable<XElement> address =
    from el in root.Elements(aw + "Address")
    where (string)el.Attribute(aw + "Type") == "Billing"
    select el;
foreach (XElement el in address)
    Console.WriteLine(el);
```

```vb
Imports <xmlns:aw='http://www.adventure-works.com'>

Module Module1
    Sub Main()
        Dim root As XElement = XElement.Load("PurchaseOrderInNamespace.xml")
        Dim address As IEnumerable(Of XElement) = _
            From el In root.<aw:Address> _
            Where el.@aw:Type = "Billing" _
            Select el
        For Each el As XElement In address
            Console.WriteLine(el)
        Next
    End Sub
End Module
```

Ten przykład generuje następujące dane wyjściowe::

```xml
<aw:Address aw:Type="Billing" xmlns:aw="http://www.adventure-works.com">
  <aw:Name>Tai Yee</aw:Name>
  <aw:Street>8 Oak Avenue</aw:Street>
  <aw:City>Old Town</aw:City>
  <aw:State>PA</aw:State>
  <aw:Zip>95819</aw:Zip>
  <aw:Country>USA</aw:Country>
</aw:Address>
```

## <a name="see-also"></a>Zobacz też

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [Standardowe operatory zapytań — Omówienie (C#)](../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Operacje projekcji (C#)](../../csharp/programming-guide/concepts/linq/projection-operations.md)
- [Zapytania podstawowe (LINQ to XML) (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [Standardowe operatory zapytań — Omówienie (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Operacje projekcji (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
