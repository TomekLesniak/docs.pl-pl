---
title: Jak utworzyć łańcuch wywołań metod osi — LINQ to XML
description: Dowiedz się, jak używać metod XContainer. elementów i Extensions. elementy, aby znaleźć wszystkie elementy określonej nazwy na danej głębokości drzewa.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 067e6da2-ee32-486d-803c-e611b328e39a
ms.openlocfilehash: 23d3b5a3dacbc56a570a92178cb8e28482907ca1
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553496"
---
# <a name="how-to-chain-axis-method-calls-linq-to-xml"></a><span data-ttu-id="1aded-103">Sposób łączenia łańcuchowo wywołań metody osi (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="1aded-103">How to chain axis method calls (LINQ to XML)</span></span>

<span data-ttu-id="1aded-104">Typowym wzorcem, który będzie używany w kodzie, jest wywołanie metody osi, a następnie wywołanie jednej z osi metody rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="1aded-104">A common pattern that you will use in your code is to call an axis method, then call one of the extension method axes.</span></span>

<span data-ttu-id="1aded-105">Istnieją dwie osie z nazwą `Elements` , która zwraca kolekcję elementów: <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> metodę i <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> metodę.</span><span class="sxs-lookup"><span data-stu-id="1aded-105">There are two axes with the name of `Elements` that return a collection of elements: the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> method and the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1aded-106">Można połączyć te dwie osie, aby znaleźć wszystkie elementy określonej nazwy na danej głębokości drzewa.</span><span class="sxs-lookup"><span data-stu-id="1aded-106">You can combine these two axes to find all elements of a specified name at a given depth in the tree.</span></span>

## <a name="example-retrieve-all-name-elements"></a><span data-ttu-id="1aded-107">Przykład: Pobierz wszystkie elementy nazwy</span><span class="sxs-lookup"><span data-stu-id="1aded-107">Example: Retrieve all name elements</span></span>

<span data-ttu-id="1aded-108">Ten przykład używa <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> i <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> do pobierania wszystkich `Name` elementów we wszystkich elementach `Address` we wszystkich `PurchaseOrder` elementach.</span><span class="sxs-lookup"><span data-stu-id="1aded-108">This example uses <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> and <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> to retrieve all `Name` elements in all `Address` elements in all `PurchaseOrder` elements.</span></span>

<span data-ttu-id="1aded-109">Ten przykład używa [przykładowego pliku XML dokumentu XML: wiele zamówień zakupu](sample-xml-file-multiple-purchase-orders.md).</span><span class="sxs-lookup"><span data-stu-id="1aded-109">This example uses XML document [Sample XML file: Multiple purchase orders](sample-xml-file-multiple-purchase-orders.md).</span></span>

```csharp
XElement purchaseOrders = XElement.Load("PurchaseOrders.xml");
IEnumerable<XElement> names =
    from el in purchaseOrders
        .Elements("PurchaseOrder")
        .Elements("Address")
        .Elements("Name")
    select el;
foreach (XElement e in names)
    Console.WriteLine(e);
```

```vb
Dim purchaseOrders As XElement = XElement.Load("PurchaseOrders.xml")
Dim names As IEnumerable(Of XElement) = _
    From el In purchaseOrders.<PurchaseOrder>.<Address>.<Name> _
    Select el
For Each e As XElement In names
    Console.WriteLine(e)
Next
```

<span data-ttu-id="1aded-110">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1aded-110">This example produces the following output:</span></span>

```xml
<Name>Ellen Adams</Name>
<Name>Tai Yee</Name>
<Name>Cristian Osorio</Name>
<Name>Cristian Osorio</Name>
<Name>Jessica Arnold</Name>
<Name>Jessica Arnold</Name>
```

<span data-ttu-id="1aded-111">To działa, ponieważ jedna z implementacji `Elements` osi jest metodą rozszerzenia w systemie <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XContainer> .</span><span class="sxs-lookup"><span data-stu-id="1aded-111">This works because one of the implementations of the `Elements` axis is as an extension method on <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="1aded-112"><xref:System.Xml.Linq.XElement> pochodzi z <xref:System.Xml.Linq.XContainer> , więc można wywołać <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> metodę w wyniku wywołania <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="1aded-112"><xref:System.Xml.Linq.XElement> derives from <xref:System.Xml.Linq.XContainer>, so you can call the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> method on the results of a call to the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> method.</span></span>

## <a name="example-retrieve-all-elements-at-a-particular-depth"></a><span data-ttu-id="1aded-113">Przykład: Pobierz wszystkie elementy z określoną głębokością</span><span class="sxs-lookup"><span data-stu-id="1aded-113">Example: Retrieve all elements at a particular depth</span></span>

<span data-ttu-id="1aded-114">Czasami chcesz pobrać wszystkie elementy z konkretnej głębokości elementu, gdy nie ma żadnych elementów nadrzędnych.</span><span class="sxs-lookup"><span data-stu-id="1aded-114">Sometimes you want to retrieve all elements at a particular element depth when there may not be intervening ancestors.</span></span> <span data-ttu-id="1aded-115">Na przykład w poniższym dokumencie warto pobrać wszystkie `ConfigParameter` elementy, które są elementami podrzędnymi `Customer` elementu, ale nie jest to element `ConfigParameter` podrzędny `Root` elementu.</span><span class="sxs-lookup"><span data-stu-id="1aded-115">For example, in the following document, you might want to retrieve all the `ConfigParameter` elements that are children of the `Customer` element, but not the `ConfigParameter` that's a child of the `Root` element.</span></span>

```xml
<Root>
  <ConfigParameter>RootConfigParameter</ConfigParameter>
  <Customer>
    <Name>Frank</Name>
    <Config>
      <ConfigParameter>FirstConfigParameter</ConfigParameter>
    </Config>
  </Customer>
  <Customer>
    <Name>Bob</Name>
    <!--This customer doesn't have a Config element-->
  </Customer>
  <Customer>
    <Name>Bill</Name>
    <Config>
      <ConfigParameter>SecondConfigParameter</ConfigParameter>
    </Config>
  </Customer>
</Root>
```

 <span data-ttu-id="1aded-116">W tym celu można użyć <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> osi w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="1aded-116">To do this, you can use the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> axis, as follows:</span></span>

```csharp
XElement root = XElement.Load("Irregular.xml");
IEnumerable<XElement> configParameters =
    root.Elements("Customer").Elements("Config").
    Elements("ConfigParameter");
foreach (XElement cp in configParameters)
    Console.WriteLine(cp);
```

```vb
Dim root As XElement = XElement.Load("Irregular.xml")
Dim configParameters As IEnumerable(Of XElement) = _
    root.<Customer>.<Config>.<ConfigParameter>
For Each cp As XElement In configParameters
    Console.WriteLine(cp)
Next
```

<span data-ttu-id="1aded-117">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1aded-117">This example produces the following output:</span></span>

```xml
<ConfigParameter>FirstConfigParameter</ConfigParameter>
<ConfigParameter>SecondConfigParameter</ConfigParameter>
```

## <a name="example-retrieve-elements-for-xml-thats-in-a-namespace"></a><span data-ttu-id="1aded-118">Przykład: pobieranie elementów dla XML znajdujących się w przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="1aded-118">Example: Retrieve elements for XML that's in a namespace</span></span>

<span data-ttu-id="1aded-119">Poniższy przykład pokazuje tę samą technikę dla XML, która znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="1aded-119">The following example shows the same technique for XML that's in a namespace.</span></span> <span data-ttu-id="1aded-120">Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1aded-120">For more information, see [Namespaces overview](namespaces-overview.md).</span></span>

<span data-ttu-id="1aded-121">Ten przykład używa [przykładowego pliku XML dokumentu XML: wiele zamówień zakupu w przestrzeni nazw](sample-xml-file-multiple-purchase-orders-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="1aded-121">This example uses XML document [Sample XML file: Multiple purchase orders in a namespace](sample-xml-file-multiple-purchase-orders-namespace.md).</span></span>

```csharp
XNamespace aw = "http://www.adventure-works.com";
XElement purchaseOrders = XElement.Load("PurchaseOrdersInNamespace.xml");
IEnumerable<XElement> names =
    from el in purchaseOrders
        .Elements(aw + "PurchaseOrder")
        .Elements(aw + "Address")
        .Elements(aw + "Name")
    select el;
foreach (XElement e in names)
    Console.WriteLine(e);
```

```vb
Imports <xmlns:aw="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim purchaseOrders As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")
        Dim names As IEnumerable(Of XElement) = _
            From el In purchaseOrders.<aw:PurchaseOrder>.<aw:Address>.<aw:Name> _
            Select el
        For Each e As XElement In names
            Console.WriteLine(e)
        Next
    End Sub
End Module
```

<span data-ttu-id="1aded-122">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="1aded-122">This example produces the following output:</span></span>

```xml
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>
```

## <a name="see-also"></a><span data-ttu-id="1aded-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1aded-123">See also</span></span>

- [<span data-ttu-id="1aded-124">Przegląd osi LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="1aded-124">LINQ to XML axes overview</span></span>](linq-xml-axes-overview.md)
