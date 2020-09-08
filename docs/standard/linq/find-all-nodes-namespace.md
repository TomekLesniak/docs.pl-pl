---
title: Jak znaleźć wszystkie węzły w przestrzeni nazw — LINQ to XML
description: Można filtrować według przestrzeni nazw każdego elementu lub atrybutu, aby znaleźć wszystkie węzły w danej przestrzeni nazw.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 3a38b913-a53e-4d0e-a19d-8782bffd3364
ms.openlocfilehash: 2041afc3e061aa89e9be5832c9d6fd5bab7a38d8
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552903"
---
# <a name="how-to-find-all-nodes-in-a-namespace-linq-to-xml"></a><span data-ttu-id="dfd0d-103">Jak znaleźć wszystkie węzły w przestrzeni nazw (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="dfd0d-103">How to find all nodes in a namespace (LINQ to XML)</span></span>

<span data-ttu-id="dfd0d-104">Można filtrować według przestrzeni nazw każdego elementu lub atrybutu, aby znaleźć wszystkie węzły w danej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="dfd0d-104">You can filter on the namespace of each element or attribute to find all nodes in that particular namespace.</span></span>

## <a name="example-create-an-xml-tree-with-two-namespaces-and-print-contents-of-one"></a><span data-ttu-id="dfd0d-105">Przykład: Tworzenie drzewa XML z dwoma przestrzeniami nazw i drukowanie zawartości jednego</span><span class="sxs-lookup"><span data-stu-id="dfd0d-105">Example: Create an XML tree with two namespaces, and print contents of one</span></span>

<span data-ttu-id="dfd0d-106">Poniższy przykład tworzy drzewo XML z dwoma przestrzeniami nazw.</span><span class="sxs-lookup"><span data-stu-id="dfd0d-106">The following example creates an XML tree with two namespaces.</span></span> <span data-ttu-id="dfd0d-107">Następnie wykonuje iterację w drzewie i drukuje nazwy wszystkich elementów i atrybutów w jednej z tych przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="dfd0d-107">It then iterates through the tree and prints the names of all the elements and attributes in one of those namespaces.</span></span>

```csharp
string markup = @"<aw:Root xmlns:aw='http://www.adventure-works.com' xmlns:fc='www.fourthcoffee.com'>
  <fc:Child1>abc</fc:Child1>
  <fc:Child2>def</fc:Child2>
  <aw:Child3>ghi</aw:Child3>
  <fc:Child4>
    <fc:GrandChild1>jkl</fc:GrandChild1>
    <aw:GrandChild2>mno</aw:GrandChild2>
  </fc:Child4>
</aw:Root>";
XElement xmlTree = XElement.Parse(markup);
Console.WriteLine("Nodes in the http://www.adventure-works.com namespace");
IEnumerable<XElement> awElements =
    from el in xmlTree.Descendants()
    where el.Name.Namespace == "http://www.adventure-works.com"
    select el;
foreach (XElement el in awElements)
    Console.WriteLine(el.Name.ToString());
```

```vb
Imports <xmlns:aw="http://www.adventure-works.com">
Imports <xmlns:fc="www.fourthcoffee.com">

Module Module1
    Sub Main()
        Dim xmlTree As XElement = _
            <aw:Root>
                <fc:Child1>abc</fc:Child1>
                <fc:Child2>def</fc:Child2>
                <aw:Child3>ghi</aw:Child3>
                <fc:Child4>
                    <fc:GrandChild1>jkl</fc:GrandChild1>
                    <aw:GrandChild2>mno</aw:GrandChild2>
                </fc:Child4>
            </aw:Root>
        Console.WriteLine("Nodes in the http://www.adventure-works.com namespace")
        Dim awElements As IEnumerable(Of XElement) = _
            From el In xmlTree.Descendants() _
            Where (el.Name.Namespace = GetXmlNamespace(aw)) _
            Select el
        For Each el As XElement In awElements
            Console.WriteLine(el.Name.ToString())
        Next
    End Sub
End Module
```

<span data-ttu-id="dfd0d-108">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="dfd0d-108">This example produces the following output:</span></span>

```output
Nodes in the http://www.adventure-works.com namespace
{http://www.adventure-works.com}Child3
{http://www.adventure-works.com}GrandChild2
```

## <a name="example-create-an-xml-tree-from-one-of-two-namespaces-contained-in-a-file"></a><span data-ttu-id="dfd0d-109">Przykład: Utwórz drzewo XML z jednego z dwóch przestrzeni nazw zawartych w pliku</span><span class="sxs-lookup"><span data-stu-id="dfd0d-109">Example: Create an XML tree from one of two namespaces contained in a file</span></span>

<span data-ttu-id="dfd0d-110">[Przykładowy plik XML dokumentu XML: skonsolidowane zamówienia zakupu](sample-xml-file-consolidated-purchase-orders.md) zawierają zamówienia zakupu w dwóch różnych przestrzeniach nazw.</span><span class="sxs-lookup"><span data-stu-id="dfd0d-110">XML document [Sample XML file: Consolidated purchase orders](sample-xml-file-consolidated-purchase-orders.md) contains purchase orders in two different namespaces.</span></span> <span data-ttu-id="dfd0d-111">Następujące zapytanie tworzy nowe drzewo z elementów jednego z nich.</span><span class="sxs-lookup"><span data-stu-id="dfd0d-111">The following query creates a new tree from the elements of one of them.</span></span>

```csharp
XDocument cpo = XDocument.Load("ConsolidatedPurchaseOrders.xml");
XNamespace aw = "http://www.adventure-works.com";
XElement newTree = new XElement("Root",
    from el in cpo.Root.Elements()
    where el.Name.Namespace == aw
    select el
);
Console.WriteLine(newTree);
```

```vb
Imports <xmlns:aw="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim cpo As XDocument = XDocument.Load("ConsolidatedPurchaseOrders.xml")
        Dim newTree As XElement = _
            <Root>
                <%= From el In cpo.Root.Elements() _
                    Where el.Name.Namespace = GetXmlNamespace(aw) _
                    Select el %>
            </Root>
        Console.WriteLine(newTree)
    End Sub
End Module
```

<span data-ttu-id="dfd0d-112">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="dfd0d-112">This example produces the following output:</span></span>

```xml
<Root>
  <aw:PurchaseOrder PONumber="11223" Date="2000-01-15" xmlns:aw="http://www.adventure-works.com">
    <aw:ShippingAddress>
      <aw:Name>Chris Preston</aw:Name>
      <aw:Street>123 Main St.</aw:Street>
      <aw:City>Seattle</aw:City>
      <aw:State>WA</aw:State>
      <aw:Zip>98113</aw:Zip>
      <aw:Country>USA</aw:Country>
    </aw:ShippingAddress>
    <aw:BillingAddress>
      <aw:Name>Chris Preston</aw:Name>
      <aw:Street>123 Main St.</aw:Street>
      <aw:City>Seattle</aw:City>
      <aw:State>WA</aw:State>
      <aw:Zip>98113</aw:Zip>
      <aw:Country>USA</aw:Country>
    </aw:BillingAddress>
    <aw:DeliveryInstructions>Ship only complete order.</aw:DeliveryInstructions>
    <aw:Item PartNum="LIT-01">
      <aw:ProductID>Litware Networking Card</aw:ProductID>
      <aw:Qty>1</aw:Qty>
      <aw:Price>20.99</aw:Price>
    </aw:Item>
    <aw:Item PartNum="LIT-25">
      <aw:ProductID>Litware 17in LCD Monitor</aw:ProductID>
      <aw:Qty>1</aw:Qty>
      <aw:Price>199.99</aw:Price>
    </aw:Item>
  </aw:PurchaseOrder>
</Root>
```
