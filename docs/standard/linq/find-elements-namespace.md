---
title: Jak znaleźć elementy w przestrzeni nazw — LINQ to XML
description: Dowiedz się, jak znaleźć elementy w określonej przestrzeni nazw przy użyciu prefiksów przestrzeni nazw w wyrażeniach XPath.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: cae1c4ac-6cd5-46cf-9b1c-bd85bc9b7ea9m
ms.openlocfilehash: db1eb39bd5e91a1f3f096743884533e979d96077
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545682"
---
# <a name="how-to-find-elements-in-a-namespace-linq-to-xml"></a><span data-ttu-id="53612-103">Jak znaleźć elementy w przestrzeni nazw (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="53612-103">How to find elements in a namespace (LINQ to XML)</span></span>

<span data-ttu-id="53612-104">Użyj prefiksów przestrzeni nazw w wyrażeniach XPath, aby znaleźć węzły w określonej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="53612-104">Use namespace prefixes in XPath expressions to find nodes in a particular namespace.</span></span> <span data-ttu-id="53612-105">Aby przeanalizować wyrażenie XPath zawierające prefiksy przestrzeni nazw, należy przekazać obiekt do metod XPath, które implementują <xref:System.Xml.IXmlNamespaceResolver> .</span><span class="sxs-lookup"><span data-stu-id="53612-105">To parse an XPath expression that contains namespace prefixes, you pass an object to the XPath methods that implement <xref:System.Xml.IXmlNamespaceResolver>.</span></span>

## <a name="example-find-purchase-orders-from-a-specific-namespace-in-a-document-that-has-two-namespaces"></a><span data-ttu-id="53612-106">Przykład: Znajdź zamówienia zakupu z określonego obszaru nazw w dokumencie, który ma dwie przestrzenie nazw</span><span class="sxs-lookup"><span data-stu-id="53612-106">Example: Find purchase orders from a specific namespace in a document that has two namespaces</span></span>

<span data-ttu-id="53612-107">W poniższym przykładzie jest używany <xref:System.Xml.XmlReader> do odczytywania [pliku XML przykładowego dokumentu XML: skonsolidowane zamówienia zakupu](sample-xml-file-consolidated-purchase-orders.md), które mają zamówienia zakupu w dwóch przestrzeniach nazw.</span><span class="sxs-lookup"><span data-stu-id="53612-107">The following example uses an <xref:System.Xml.XmlReader> to read XML document [Sample XML file: Consolidated purchase orders](sample-xml-file-consolidated-purchase-orders.md), which has purchase orders in two namespaces.</span></span> <span data-ttu-id="53612-108">Następnie pobiera <xref:System.Xml.XmlNameTable> z <xref:System.Xml.XmlReader> i z <xref:System.Xml.XmlNamespaceManager> <xref:System.Xml.XmlNameTable> .</span><span class="sxs-lookup"><span data-stu-id="53612-108">It then gets an <xref:System.Xml.XmlNameTable> from the <xref:System.Xml.XmlReader>, and an <xref:System.Xml.XmlNamespaceManager> from the <xref:System.Xml.XmlNameTable>.</span></span> <span data-ttu-id="53612-109">Używa <xref:System.Xml.XmlNamespaceManager> podczas wybierania elementów.</span><span class="sxs-lookup"><span data-stu-id="53612-109">It uses the <xref:System.Xml.XmlNamespaceManager> when selecting elements.</span></span>

<span data-ttu-id="53612-110">Wyrażenie XPath: `./aw:*`</span><span class="sxs-lookup"><span data-stu-id="53612-110">The XPath expression is: `./aw:*`</span></span>

```csharp
XmlReader reader = XmlReader.Create("ConsolidatedPurchaseOrders.xml");
XElement root = XElement.Load(reader);
XmlNameTable nameTable = reader.NameTable;
XmlNamespaceManager namespaceManager = new XmlNamespaceManager(nameTable);
namespaceManager.AddNamespace("aw", "http://www.adventure-works.com");
IEnumerable<XElement> list1 = root.XPathSelectElements("./aw:*", namespaceManager);
IEnumerable<XElement> list2 =
    from el in root.Elements()
    where el.Name.Namespace == "http://www.adventure-works.com"
    select el;
if (list1.Count() == list2.Count() &&
        list1.Intersect(list2).Count() == list1.Count())
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
foreach (XElement el in list2)
    Console.WriteLine(el);
```

```vb
Dim reader As XmlReader = _
        XmlReader.Create("ConsolidatedPurchaseOrders.xml")
Dim root As XElement = XElement.Load(reader)
Dim nameTable As XmlNameTable = reader.NameTable
Dim namespaceManager As XmlNamespaceManager = New XmlNamespaceManager(nameTable)
namespaceManager.AddNamespace("aw", "http://www.adventure-works.com")

Dim list1 As IEnumerable(Of XElement) = _
        root.XPathSelectElements("./aw:*", namespaceManager)
Dim list2 As IEnumerable(Of XElement) = _
    From el In root.Elements() _
    Where el.Name.Namespace = "http://www.adventure-works.com" _
    Select el

If list1.Count() = list2.Count() And _
        list1.Intersect(list2).Count() = list1.Count() Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
For Each el As XElement In list2
    Console.WriteLine(el)
Next
```

<span data-ttu-id="53612-111">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="53612-111">This example produces the following output:</span></span>

```output
Results are identical
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
```

## <a name="see-also"></a><span data-ttu-id="53612-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="53612-112">See also</span></span>

- [<span data-ttu-id="53612-113">LINQ to XML dla użytkowników XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53612-113">LINQ to XML for XPath Users (Visual Basic)</span></span>](./comparison-xpath-linq-xml.md)
