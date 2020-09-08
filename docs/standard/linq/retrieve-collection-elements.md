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
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml"></a><span data-ttu-id="21322-103">Pobieranie kolekcji elementów (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="21322-103">How to retrieve a collection of elements (LINQ to XML)</span></span>

<span data-ttu-id="21322-104">W tym artykule przedstawiono <xref:System.Xml.Linq.XContainer.Elements%2A> metodę, która pobiera kolekcję elementów podrzędnych elementu.</span><span class="sxs-lookup"><span data-stu-id="21322-104">This article demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method, which retrieves a collection of the child elements of an element.</span></span>

## <a name="example-iterate-through-the-child-elements-of-an-element"></a><span data-ttu-id="21322-105">Przykład: Iterowanie przez elementy podrzędne elementu</span><span class="sxs-lookup"><span data-stu-id="21322-105">Example: Iterate through the child elements of an element</span></span>

<span data-ttu-id="21322-106">Ten przykład wykonuje iterację przez elementy podrzędne `purchaseOrder` elementu.</span><span class="sxs-lookup"><span data-stu-id="21322-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span> <span data-ttu-id="21322-107">Używa [przykładowego pliku XML dokumentu XML: typowe zamówienie zakupu](sample-xml-file-typical-purchase-order.md).</span><span class="sxs-lookup"><span data-stu-id="21322-107">It uses XML document [Sample XML file: Typical purchase order](sample-xml-file-typical-purchase-order.md).</span></span>

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

<span data-ttu-id="21322-108">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="21322-108">This example produces the following output:</span></span>

```output
Name: Address
Name: Address
Name: DeliveryNotes
Name: Items
```

## <a name="see-also"></a><span data-ttu-id="21322-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="21322-109">See also</span></span>

- [<span data-ttu-id="21322-110">Przegląd osi LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="21322-110">LINQ to XML axes overview</span></span>](linq-xml-axes-overview.md)
