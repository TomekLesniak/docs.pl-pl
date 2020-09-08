---
title: Jak znaleźć element główny — LINQ to XML
description: Dowiedz się, jak używać XPath i LINQ to XML w językach C# i Visual Basic, aby znaleźć element główny dokumentu XML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: 16217960b84276bd3bb4c5cb6b38d7cb56d2b41e
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553161"
---
# <a name="how-to-find-the-root-element-linq-to-xml"></a><span data-ttu-id="cc1c1-103">Jak znaleźć element główny (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="cc1c1-103">How to find the root element (LINQ to XML)</span></span>

<span data-ttu-id="cc1c1-104">W tym artykule przedstawiono przykład, w którym pokazano, jak używać XPath i LINQ to XML w języku C# i Visual Basic, aby znaleźć element główny dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="cc1c1-104">This article provides an example that shows how to use XPath and LINQ to XML, in C# and Visual Basic, to find the root element of an XML document.</span></span>

## <a name="example-find-the-root-element"></a><span data-ttu-id="cc1c1-105">Przykład: Znajdź element główny</span><span class="sxs-lookup"><span data-stu-id="cc1c1-105">Example: Find the root element</span></span>

<span data-ttu-id="cc1c1-106">W tym przykładzie używamy zapytania LINQ to XML i XPath, aby znaleźć element główny w [przykładowym pliku XML dokumentu XML: wiele zamówień zakupu](sample-xml-file-multiple-purchase-orders.md).</span><span class="sxs-lookup"><span data-stu-id="cc1c1-106">This example uses LINQ to XML query and XPath to find the root element in XML document [Sample XML file: Multiple purchase orders](sample-xml-file-multiple-purchase-orders.md).</span></span> <span data-ttu-id="cc1c1-107">Wyrażenie XPath ma wartość `/PurchaseOrders` .</span><span class="sxs-lookup"><span data-stu-id="cc1c1-107">The XPath expression is `/PurchaseOrders`.</span></span>

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

<span data-ttu-id="cc1c1-108">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="cc1c1-108">This example produces the following output:</span></span>

```output
Results are identical
PurchaseOrders
```

## <a name="see-also"></a><span data-ttu-id="cc1c1-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cc1c1-109">See also</span></span>

- [<span data-ttu-id="cc1c1-110">LINQ to XML dla użytkowników XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc1c1-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](/../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
