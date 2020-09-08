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
# <a name="how-to-write-queries-with-complex-filtering-linq-to-xml"></a><span data-ttu-id="99b70-104">Jak pisać zapytania z skomplikowanym filtrowaniem (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="99b70-104">How to write queries with complex filtering (LINQ to XML)</span></span>

<span data-ttu-id="99b70-105">Czasami chcesz pisać zapytania LINQ to XML ze złożonymi filtrami.</span><span class="sxs-lookup"><span data-stu-id="99b70-105">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="99b70-106">Na przykład może być konieczne znalezienie wszystkich elementów, które mają element podrzędny o określonej nazwie i wartości.</span><span class="sxs-lookup"><span data-stu-id="99b70-106">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="99b70-107">Ten artykuł zawiera przykład tworzenia zapytania z skomplikowanym filtrowaniem.</span><span class="sxs-lookup"><span data-stu-id="99b70-107">This article gives an example of writing a query with complex filtering.</span></span>

## <a name="example-find-with-a-nested-query-in-the-where-clause"></a><span data-ttu-id="99b70-108">Przykład: Znajdź z zagnieżdżonym zapytaniem w `Where` klauzuli</span><span class="sxs-lookup"><span data-stu-id="99b70-108">Example: Find with a nested query in the `Where` clause</span></span>

<span data-ttu-id="99b70-109">Ten przykład pokazuje, jak znaleźć wszystkie `PurchaseOrder` elementy, które mają:</span><span class="sxs-lookup"><span data-stu-id="99b70-109">This example shows how to find all `PurchaseOrder` elements that have:</span></span>

- <span data-ttu-id="99b70-110">Element podrzędny, `Address` którego `Type` atrybut ma wartość "wysyłka".</span><span class="sxs-lookup"><span data-stu-id="99b70-110">A child `Address` element whose `Type` attribute equals "Shipping".</span></span>
- <span data-ttu-id="99b70-111">Element podrzędny `State` , który jest równy "NY".</span><span class="sxs-lookup"><span data-stu-id="99b70-111">A child `State` element that equals "NY".</span></span>

<span data-ttu-id="99b70-112">Używa zapytania zagnieżdżonego w `Where` klauzuli i `Any` operator zwraca, `true` Jeśli kolekcja zawiera jakiekolwiek elementy.</span><span class="sxs-lookup"><span data-stu-id="99b70-112">It uses a nested query in the `Where` clause, and the `Any` operator returns `true` if the collection has any elements in it.</span></span> <span data-ttu-id="99b70-113">W przykładzie zastosowano [przykładowy plik XML dokumentu XML: wiele zamówień zakupu](sample-xml-file-multiple-purchase-orders.md).</span><span class="sxs-lookup"><span data-stu-id="99b70-113">The example uses XML document [Sample XML file: Multiple purchase orders](sample-xml-file-multiple-purchase-orders.md).</span></span>

<span data-ttu-id="99b70-114">Aby uzyskać więcej informacji na temat `Any` operatora, zobacz [Operacje kwantyfikatora (C#)](../../../docs/csharp/programming-guide/concepts/linq/quantifier-operations.md) i [Kwantyfikatory (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="99b70-114">For more information about the `Any` operator, see [Quantifier Operations (C#)](../../../docs/csharp/programming-guide/concepts/linq/quantifier-operations.md) and [Quantifier Operations (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).</span></span>

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

<span data-ttu-id="99b70-115">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="99b70-115">This example produces the following output:</span></span>

```output
99505
```

## <a name="example-find-in-xml-thats-in-a-namespace"></a><span data-ttu-id="99b70-116">Przykład: Znajdź w kodzie XML, który znajduje się w przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="99b70-116">Example: Find in XML that's in a namespace</span></span>

<span data-ttu-id="99b70-117">Poniższy przykład pokazuje takie samo zapytanie jak powyżej, ale dla kodu XML, który znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="99b70-117">The following example shows the same query as above, but for XML that's in a namespace.</span></span> <span data-ttu-id="99b70-118">Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).</span><span class="sxs-lookup"><span data-stu-id="99b70-118">For more information, see [Namespaces overview](namespaces-overview.md).</span></span>

<span data-ttu-id="99b70-119">Ten przykład używa [przykładowego pliku XML dokumentu XML: wiele zamówień zakupu w przestrzeni nazw](sample-xml-file-multiple-purchase-orders-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="99b70-119">This example uses XML document [Sample XML file: Multiple purchase orders in a namespace](sample-xml-file-multiple-purchase-orders-namespace.md).</span></span>

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

<span data-ttu-id="99b70-120">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="99b70-120">This example produces the following output:</span></span>

```output
99505
```

## <a name="see-also"></a><span data-ttu-id="99b70-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="99b70-121">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="99b70-122">Operacje projekcji (C#)</span><span class="sxs-lookup"><span data-stu-id="99b70-122">Projection Operations (C#)</span></span>](../../csharp/programming-guide/concepts/linq/projection-operations.md)
- [<span data-ttu-id="99b70-123">Operacje kwantyfikatora (C#)</span><span class="sxs-lookup"><span data-stu-id="99b70-123">Quantifier Operations (C#)</span></span>](../../csharp/programming-guide/concepts/linq/quantifier-operations.md)
- [<span data-ttu-id="99b70-124">Właściwości osi elementu podrzędnego XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99b70-124">XML Child Axis Property (Visual Basic)</span></span>](../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="99b70-125">Właściwości osi atrybutu XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99b70-125">XML Attribute Axis Property (Visual Basic)</span></span>](../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
- [<span data-ttu-id="99b70-126">Właściwość wartości XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99b70-126">XML Value Property (Visual Basic)</span></span>](../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="99b70-127">Operacje projekcji (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99b70-127">Projection Operations (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
- [<span data-ttu-id="99b70-128">Operacje kwantyfikatora (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99b70-128">Quantifier Operations (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)
