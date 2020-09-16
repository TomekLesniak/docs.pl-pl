---
title: Jak znaleźć element z określonym atrybutem — LINQ to XML
description: Dowiedz się, jak znaleźć element, którego atrybut ma określoną wartość.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: b92591aa-3cfb-490e-99f6-da8de335e362
ms.openlocfilehash: a1569f8a91e980f12ecc1801e00d6414711833d0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535461"
---
# <a name="how-to-find-an-element-with-a-specific-attribute-linq-to-xml"></a><span data-ttu-id="4ebe6-103">Jak znaleźć element z określonym atrybutem (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-103">How to find an element with a specific attribute (LINQ to XML)</span></span>

<span data-ttu-id="4ebe6-104">W tym artykule przedstawiono przykłady znajdowania elementu, którego atrybut ma określoną wartość.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-104">This article provides examples of how to find an element whose attribute has a specific value.</span></span>

## <a name="example-find-an-element-whose-attribute-has-a-specific-value"></a><span data-ttu-id="4ebe6-105">Przykład: Znajdź element, którego atrybut ma określoną wartość</span><span class="sxs-lookup"><span data-stu-id="4ebe6-105">Example: Find an element whose attribute has a specific value</span></span>

<span data-ttu-id="4ebe6-106">Poniższy przykład pokazuje, jak znaleźć `Address` element, który ma `Type` atrybut o wartości "rozliczenia".</span><span class="sxs-lookup"><span data-stu-id="4ebe6-106">The following example shows how to find the `Address` element that has a `Type` attribute with a value of "Billing".</span></span> <span data-ttu-id="4ebe6-107">W przykładzie zastosowano [przykładowy plik XML dokumentu XML: typowe zamówienie zakupu](sample-xml-file-typical-purchase-order.md).</span><span class="sxs-lookup"><span data-stu-id="4ebe6-107">The example uses XML document [Sample XML file: Typical purchase order](sample-xml-file-typical-purchase-order.md).</span></span>

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

<span data-ttu-id="4ebe6-108">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="4ebe6-108">This example produces the following output:</span></span>

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

## <a name="example-find-an-element-in-xml-thats-in-a-namespace"></a><span data-ttu-id="4ebe6-109">Przykład: Znajdź element w kodzie XML, który znajduje się w przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="4ebe6-109">Example: Find an element in XML that's in a namespace</span></span>

<span data-ttu-id="4ebe6-110">W poniższym przykładzie pokazano to samo zapytanie, ale w przypadku kodu XML, który znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="4ebe6-110">The following example shows the same query, but for XML that's in a namespace.</span></span> <span data-ttu-id="4ebe6-111">Używa [przykładowego pliku XML dokumentu XML: typowe zamówienie zakupu w przestrzeni nazw](sample-xml-file-typical-purchase-order-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="4ebe6-111">It uses XML document [Sample XML file: typical purchase order in a namespace](sample-xml-file-typical-purchase-order-namespace.md).</span></span>

<span data-ttu-id="4ebe6-112">Aby uzyskać więcej informacji na temat przestrzeni nazw, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4ebe6-112">For more information about namespaces, see [Namespaces overview](namespaces-overview.md).</span></span>

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

<span data-ttu-id="4ebe6-113">Ten przykład generuje następujące dane wyjściowe::</span><span class="sxs-lookup"><span data-stu-id="4ebe6-113">This example produces the following output::</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4ebe6-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="4ebe6-114">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="4ebe6-115">Standardowe operatory zapytań — Omówienie (C#)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-115">Standard Query Operators Overview (C#)</span></span>](../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="4ebe6-116">Operacje projekcji (C#)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-116">Projection Operations (C#)</span></span>](../../csharp/programming-guide/concepts/linq/projection-operations.md)
- [<span data-ttu-id="4ebe6-117">Zapytania podstawowe (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-117">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)
- [<span data-ttu-id="4ebe6-118">Standardowe operatory zapytań — Omówienie (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-118">Standard Query Operators Overview (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="4ebe6-119">Operacje projekcji (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ebe6-119">Projection Operations (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
