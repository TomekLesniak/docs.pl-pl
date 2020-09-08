---
title: Jak pobrać kolekcję elementów — LINQ to XML
description: Dowiedz się, jak używać metody XContainer. Elements do pobierania kolekcji elementów podrzędnych elementu.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: e73f608cff13f75f769f77372dc1c09949e00b0e
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552960"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml"></a>Pobieranie kolekcji elementów (LINQ to XML)

W tym artykule przedstawiono <xref:System.Xml.Linq.XContainer.Elements%2A> metodę, która pobiera kolekcję elementów podrzędnych elementu.

## <a name="example-iterate-through-the-child-elements-of-an-element"></a>Przykład: Iterowanie przez elementy podrzędne elementu

Ten przykład wykonuje iterację przez elementy podrzędne `purchaseOrder` elementu. Używa [przykładowego pliku XML dokumentu XML: typowe zamówienie zakupu](sample-xml-file-typical-purchase-order.md).

```csharp
XElement po = XElement.Load("PurchaseOrder.xml");
IEnumerable<XElement> childElements =
    from el in po.Elements()
    select el;
foreach (XElement el in childElements)
    Console.WriteLine("Name: " + el.Name);
```

```vb
Dim po As XElement = XElement.Load("PurchaseOrder.xml")
Dim childElements As IEnumerable(Of XElement)
childElements = _
    From el In po.Elements() _
    Select el
For Each el As XElement In childElements
    Console.WriteLine("Name: " & el.Name.ToString())
Next
```

Ten przykład generuje następujące wyniki:

```output
Name: Address
Name: Address
Name: DeliveryNotes
Name: Items
```

## <a name="see-also"></a>Zobacz też

- [Przegląd osi LINQ to XML](linq-xml-axes-overview.md)
