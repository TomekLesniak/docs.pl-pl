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
# <a name="how-to-chain-axis-method-calls-linq-to-xml"></a>Sposób łączenia łańcuchowo wywołań metody osi (LINQ to XML)

Typowym wzorcem, który będzie używany w kodzie, jest wywołanie metody osi, a następnie wywołanie jednej z osi metody rozszerzenia.

Istnieją dwie osie z nazwą `Elements` , która zwraca kolekcję elementów: <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> metodę i <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> metodę. Można połączyć te dwie osie, aby znaleźć wszystkie elementy określonej nazwy na danej głębokości drzewa.

## <a name="example-retrieve-all-name-elements"></a>Przykład: Pobierz wszystkie elementy nazwy

Ten przykład używa <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> i <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> do pobierania wszystkich `Name` elementów we wszystkich elementach `Address` we wszystkich `PurchaseOrder` elementach.

Ten przykład używa [przykładowego pliku XML dokumentu XML: wiele zamówień zakupu](sample-xml-file-multiple-purchase-orders.md).

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

Ten przykład generuje następujące wyniki:

```xml
<Name>Ellen Adams</Name>
<Name>Tai Yee</Name>
<Name>Cristian Osorio</Name>
<Name>Cristian Osorio</Name>
<Name>Jessica Arnold</Name>
<Name>Jessica Arnold</Name>
```

To działa, ponieważ jedna z implementacji `Elements` osi jest metodą rozszerzenia w systemie <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XContainer> . <xref:System.Xml.Linq.XElement> pochodzi z <xref:System.Xml.Linq.XContainer> , więc można wywołać <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> metodę w wyniku wywołania <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> metody.

## <a name="example-retrieve-all-elements-at-a-particular-depth"></a>Przykład: Pobierz wszystkie elementy z określoną głębokością

Czasami chcesz pobrać wszystkie elementy z konkretnej głębokości elementu, gdy nie ma żadnych elementów nadrzędnych. Na przykład w poniższym dokumencie warto pobrać wszystkie `ConfigParameter` elementy, które są elementami podrzędnymi `Customer` elementu, ale nie jest to element `ConfigParameter` podrzędny `Root` elementu.

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

 W tym celu można użyć <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> osi w następujący sposób:

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

Ten przykład generuje następujące wyniki:

```xml
<ConfigParameter>FirstConfigParameter</ConfigParameter>
<ConfigParameter>SecondConfigParameter</ConfigParameter>
```

## <a name="example-retrieve-elements-for-xml-thats-in-a-namespace"></a>Przykład: pobieranie elementów dla XML znajdujących się w przestrzeni nazw

Poniższy przykład pokazuje tę samą technikę dla XML, która znajduje się w przestrzeni nazw. Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

Ten przykład używa [przykładowego pliku XML dokumentu XML: wiele zamówień zakupu w przestrzeni nazw](sample-xml-file-multiple-purchase-orders-namespace.md).

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

Ten przykład generuje następujące wyniki:

```xml
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>
```

## <a name="see-also"></a>Zobacz też

- [Przegląd osi LINQ to XML](linq-xml-axes-overview.md)
