---
title: Jak znaleźć element główny — LINQ to XML
description: Dowiedz się, jak używać XPath i LINQ to XML w językach C# i Visual Basic, aby znaleźć element główny dokumentu XML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: 89247c19fc31add4e95f11742772cef1bdd2ce63
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679467"
---
# <a name="how-to-find-the-root-element-linq-to-xml"></a><span data-ttu-id="2830f-103">Jak znaleźć element główny (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="2830f-103">How to find the root element (LINQ to XML)</span></span>

<span data-ttu-id="2830f-104">W tym artykule przedstawiono przykład, w którym pokazano, jak używać XPath i LINQ to XML w języku C# i Visual Basic, aby znaleźć element główny dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="2830f-104">This article provides an example that shows how to use XPath and LINQ to XML, in C# and Visual Basic, to find the root element of an XML document.</span></span>

## <a name="example-find-the-root-element"></a><span data-ttu-id="2830f-105">Przykład: Znajdź element główny</span><span class="sxs-lookup"><span data-stu-id="2830f-105">Example: Find the root element</span></span>

<span data-ttu-id="2830f-106">W tym przykładzie używamy zapytania LINQ to XML i XPath, aby znaleźć element główny w [przykładowym pliku XML dokumentu XML: wiele zamówień zakupu](sample-xml-file-multiple-purchase-orders.md).</span><span class="sxs-lookup"><span data-stu-id="2830f-106">This example uses LINQ to XML query and XPath to find the root element in XML document [Sample XML file: Multiple purchase orders](sample-xml-file-multiple-purchase-orders.md).</span></span> <span data-ttu-id="2830f-107">Wyrażenie XPath ma wartość `/PurchaseOrders` .</span><span class="sxs-lookup"><span data-stu-id="2830f-107">The XPath expression is `/PurchaseOrders`.</span></span>

```csharp
XDocument po = XDocument.Load("PurchaseOrders.xml");

// LINQ to XML query
XElement el1 = po.Root;

// XPath expression
XElement el2 = po.XPathSelectElement("/PurchaseOrders");

if (el1 == el2)
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
Console.WriteLine(el1.Name);
```

```vb
Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")

' LINQ to XML query
Dim el1 As XElement = po.Root

' XPath expression
Dim el2 As XElement = po.XPathSelectElement("/PurchaseOrders")

If el1 Is el2 Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
Console.WriteLine(el1.Name)
```

<span data-ttu-id="2830f-108">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="2830f-108">This example produces the following output:</span></span>

```output
Results are identical
PurchaseOrders
```

## <a name="see-also"></a><span data-ttu-id="2830f-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="2830f-109">See also</span></span>

- [<span data-ttu-id="2830f-110">Porównanie metody XPath i LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="2830f-110">Comparison of XPath and LINQ to XML</span></span>](comparison-xpath-linq-xml.md)
