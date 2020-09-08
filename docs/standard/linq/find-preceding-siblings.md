---
title: Jak znaleźć poprzednie elementy równorzędne — LINQ to XML
description: 'Dowiedz się, jak znaleźć elementy równorzędne poprzedzające dany element. Pokazane są dwie metody: jeden używa XPathSelectElements wzdłuż osi poprzedzającego elementu równorzędnego, drugi używa XNode. ElementsBeforeSelf.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: b281ff99-d08a-43d0-bea1-eff831b2f8ae
ms.openlocfilehash: 788101eee6cdbce89626d1b46a5011a897c64704
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553188"
---
# <a name="how-to-find-preceding-siblings-linq-to-xml"></a>Jak znaleźć poprzednie elementy równorzędne (LINQ to XML)

W tym artykule pokazano, jak używać <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> wzdłuż osi powyższego poziomu elementów równorzędnych do znajdowania elementów równorzędnych poprzedzających dany element, a także sposobu używania <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> do znajdowania tych samych elementów.

## <a name="example-use-two-methods-to-find-sibling-elements-that-precede-an-element"></a>Przykład: Użyj dwóch metod, aby znaleźć elementy równorzędne poprzedzające element

Poniższy przykład umożliwia znalezienie `FullAddress` elementu w dokumencie XML [przykładowy plik XML: klienci i zamówienia](sample-xml-file-customers-orders.md)i pobiera poprzednie elementy równorzędne na dwa różne sposoby. Następnie porównuje wyniki i znajduje je identycznie.

> [!NOTE]
> Obie metody zapewniają wyniki w kolejności dokumentu.

Użyte wyrażenie XPath ma wartość `preceding-sibling::*` .

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

Ten przykład generuje następujące wyniki:

```output
Results are identical
<CompanyName>Great Lakes Food Market</CompanyName>
<ContactName>Howard Snyder</ContactName>
<ContactTitle>Marketing Manager</ContactTitle>
<Phone>(503) 555-7555</Phone>
```

## <a name="see-also"></a>Zobacz też

- [LINQ to XML dla użytkowników XPath (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
