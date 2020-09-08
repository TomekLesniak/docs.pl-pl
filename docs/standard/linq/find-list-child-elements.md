---
title: Jak znaleźć listę elementów podrzędnych — LINQ to XML
description: W tym artykule porównano oś elementów podrzędnych XPath z LINQ to XML osi XContainer. elementy.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 7c589dd8-f680-4cdb-9d6a-78d57e2555e8
ms.openlocfilehash: 84b820f3192a173130c485f3e7cdadf9499932f1
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553192"
---
# <a name="how-to-find-a-list-of-child-elements-linq-to-xml"></a><span data-ttu-id="750df-103">Jak znaleźć listę elementów podrzędnych (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="750df-103">How to find a list of child elements (LINQ to XML)</span></span>

<span data-ttu-id="750df-104">W tym artykule porównano oś elementów podrzędnych XPath z <xref:System.Xml.Linq.XContainer.Elements%2A> osią LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="750df-104">This article compares the XPath child elements axis to the LINQ to XML <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>

## <a name="example-find-all-child-elements-of-an-element"></a><span data-ttu-id="750df-105">Przykład: Znajdź wszystkie elementy podrzędne elementu</span><span class="sxs-lookup"><span data-stu-id="750df-105">Example: Find all child elements of an element</span></span>

<span data-ttu-id="750df-106">Ten przykład umożliwia znalezienie wszystkich elementów podrzędnych `Address` elementu w [przykładowym pliku XML dokumentu XML: wiele zamówień zakupu](sample-xml-file-multiple-purchase-orders.md).</span><span class="sxs-lookup"><span data-stu-id="750df-106">This example finds all of the child elements of the `Address` element in XML document [Sample XML file: Multiple purchase orders](sample-xml-file-multiple-purchase-orders.md).</span></span>

<span data-ttu-id="750df-107">Wyrażenie XPath: `./*`</span><span class="sxs-lookup"><span data-stu-id="750df-107">The XPath expression is: `./*`</span></span>

```csharp
XDocument cpo = XDocument.Load("PurchaseOrders.xml");
XElement po = cpo.Root.Element("PurchaseOrder").Element("Address");

// LINQ to XML query
IEnumerable<XElement> list1 = po.Elements();

// XPath expression
IEnumerable<XElement> list2 = po.XPathSelectElements("./*");

if (list1.Count() == list2.Count() &&
        list1.Intersect(list2).Count() == list1.Count())
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
foreach (XElement el in list1)
    Console.WriteLine(el);
```

```vb
Dim cpo As XDocument = XDocument.Load("PurchaseOrders.xml")
Dim po As XElement = cpo.Root.<PurchaseOrder>.<Address>.FirstOrDefault

' LINQ to XML query
Dim list1 As IEnumerable(Of XElement) = po.Elements()

' XPath expression
Dim list2 As IEnumerable(Of XElement) = po.XPathSelectElements("./*")

If (list1.Count() = list2.Count()) AndAlso _
    (list1.Intersect(list2).Count() = list1.Count()) Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
For Each el As XElement In list1
    Console.WriteLine(el)
Next
```

<span data-ttu-id="750df-108">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="750df-108">This example produces the following output:</span></span>

```output
Results are identical
<Name>Ellen Adams</Name>
<Street>123 Maple Street</Street>
<City>Mill Valley</City>
<State>CA</State>
<Zip>10999</Zip>
<Country>USA</Country>
```

## <a name="see-also"></a><span data-ttu-id="750df-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="750df-109">See also</span></span>

- [<span data-ttu-id="750df-110">LINQ to XML dla użytkowników XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="750df-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
