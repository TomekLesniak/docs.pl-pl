---
title: Jak znaleźć poprzednie elementy równorzędne — LINQ to XML
description: 'Dowiedz się, jak znaleźć elementy równorzędne poprzedzające dany element. Pokazane są dwie metody: jeden używa XPathSelectElements wzdłuż osi poprzedzającego elementu równorzędnego, drugi używa XNode. ElementsBeforeSelf.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: b281ff99-d08a-43d0-bea1-eff831b2f8ae
ms.openlocfilehash: 0cfd516f274eaf2940a7b944d34c6ea494e7eaa1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546190"
---
# <a name="how-to-find-preceding-siblings-linq-to-xml"></a><span data-ttu-id="208cb-104">Jak znaleźć poprzednie elementy równorzędne (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="208cb-104">How to find preceding siblings (LINQ to XML)</span></span>

<span data-ttu-id="208cb-105">W tym artykule pokazano, jak używać <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> wzdłuż osi powyższego poziomu elementów równorzędnych do znajdowania elementów równorzędnych poprzedzających dany element, a także sposobu używania <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> do znajdowania tych samych elementów.</span><span class="sxs-lookup"><span data-stu-id="208cb-105">This article shows how to use <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> along the preceding-sibling axis to find sibling elements that precede a given element, and how to use <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> to find the same elements.</span></span>

## <a name="example-use-two-methods-to-find-sibling-elements-that-precede-an-element"></a><span data-ttu-id="208cb-106">Przykład: Użyj dwóch metod, aby znaleźć elementy równorzędne poprzedzające element</span><span class="sxs-lookup"><span data-stu-id="208cb-106">Example: Use two methods to find sibling elements that precede an element</span></span>

<span data-ttu-id="208cb-107">Poniższy przykład umożliwia znalezienie `FullAddress` elementu w dokumencie XML [przykładowy plik XML: klienci i zamówienia](sample-xml-file-customers-orders.md)i pobiera poprzednie elementy równorzędne na dwa różne sposoby.</span><span class="sxs-lookup"><span data-stu-id="208cb-107">The following example finds the `FullAddress` element in XML document [Sample XML file: Customers and orders](sample-xml-file-customers-orders.md), and retrieves the preceding sibling elements in two different ways.</span></span> <span data-ttu-id="208cb-108">Następnie porównuje wyniki i znajduje je identycznie.</span><span class="sxs-lookup"><span data-stu-id="208cb-108">It then compares the results and finds them identical.</span></span>

> [!NOTE]
> <span data-ttu-id="208cb-109">Obie metody zapewniają wyniki w kolejności dokumentu.</span><span class="sxs-lookup"><span data-stu-id="208cb-109">Both methods provide results that are in document order.</span></span>

<span data-ttu-id="208cb-110">Użyte wyrażenie XPath ma wartość `preceding-sibling::*` .</span><span class="sxs-lookup"><span data-stu-id="208cb-110">The XPath expression used is `preceding-sibling::*`.</span></span>

```csharp
XElement co = XElement.Load("CustomersOrders.xml");

XElement add = co.Element("Customers").Element("Customer").Element("FullAddress");

// LINQ to XML query
IEnumerable<XElement> list1 = add.ElementsBeforeSelf();

// XPath expression
IEnumerable<XElement> list2 = add.XPathSelectElements("preceding-sibling::*");

if (list1.Count() == list2.Count() &&
        list1.Intersect(list2).Count() == list1.Count())
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
foreach (XElement el in list2)
    Console.WriteLine(el);
```

```vb
Dim co As XElement = XElement.Load("CustomersOrders.xml")
Dim add As XElement = co.<Customers>.<Customer>. _
        <FullAddress>.FirstOrDefault

' LINQ to XML query
Dim list1 As IEnumerable(Of XElement) = add.ElementsBeforeSelf()

' XPath expression
Dim list2 As IEnumerable(Of XElement) = add.XPathSelectElements("preceding-sibling::*")

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

<span data-ttu-id="208cb-111">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="208cb-111">This example produces the following output:</span></span>

```output
Results are identical
<CompanyName>Great Lakes Food Market</CompanyName>
<ContactName>Howard Snyder</ContactName>
<ContactTitle>Marketing Manager</ContactTitle>
<Phone>(503) 555-7555</Phone>
```

## <a name="see-also"></a><span data-ttu-id="208cb-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="208cb-112">See also</span></span>

- [<span data-ttu-id="208cb-113">LINQ to XML dla użytkowników XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="208cb-113">LINQ to XML for XPath Users (Visual Basic)</span></span>](./comparison-xpath-linq-xml.md)
