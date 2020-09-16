---
title: Jak znaleźć powiązane elementy — LINQ to XML
description: Dowiedz się, jak używać zapytań LINQ to XML i XPath w językach C# i Visual Basic, aby znaleźć wartość jednego elementu i elementu, którego atrybut ma taką samą wartość.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 41b386ee-562d-4841-bd6b-e44a7eb69f26
ms.openlocfilehash: 385d454d19a12bfa0f90510d73a2961a93bbd5ee
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549606"
---
# <a name="how-to-find-related-elements-linq-to-xml"></a><span data-ttu-id="95601-103">Jak znaleźć powiązane elementy (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="95601-103">How to find related elements (LINQ to XML)</span></span>

<span data-ttu-id="95601-104">W tym artykule pokazano, jak używać zapytań LINQ to XML i XPath w językach C# i Visual Basic, aby znaleźć wartość jednego elementu i elementu, którego atrybut ma taką samą wartość.</span><span class="sxs-lookup"><span data-stu-id="95601-104">This article shows how to use LINQ to XML query and XPath, in C# and Visual Basic, to find the value of one element and an element whose attribute has the same value.</span></span>

## <a name="example-find-the-value-of-one-element-and-an-element-whose-attribute-has-the-same-value"></a><span data-ttu-id="95601-105">Przykład: Znajdź wartość jednego elementu i elementu, którego atrybut ma taką samą wartość</span><span class="sxs-lookup"><span data-stu-id="95601-105">Example: Find the value of one element and an element whose attribute has the same value</span></span>

<span data-ttu-id="95601-106">Ten przykład umożliwia znalezienie dwunastego `Order` elementu w dokumencie XML [przykładowy plik XML: klienci i zamówienia](sample-xml-file-customers-orders.md), a następnie znajduje klienta dla tej kolejności.</span><span class="sxs-lookup"><span data-stu-id="95601-106">This example finds the 12th `Order` element in XML document [Sample XML file: Customers and orders](sample-xml-file-customers-orders.md), and then finds the customer for that order.</span></span> <span data-ttu-id="95601-107">Wyrażenie XPath ma wartość `.//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]` .</span><span class="sxs-lookup"><span data-stu-id="95601-107">The XPath expression is `.//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]`.</span></span>

> [!NOTE]
> <span data-ttu-id="95601-108">W programie .NET indeksowanie do listy jest zależne od zera. oznacza to, że indeks 0 odwołuje się do elementu początkowego.</span><span class="sxs-lookup"><span data-stu-id="95601-108">In .NET, the indexing into a list is zero-based; that is, an index of 0 refers to the initial element.</span></span> <span data-ttu-id="95601-109">Indeksowanie do kolekcji węzłów w predykacie XPath jest oparte na jednym z nich.</span><span class="sxs-lookup"><span data-stu-id="95601-109">Indexing into a collection of nodes in an XPath predicate is one-based.</span></span> <span data-ttu-id="95601-110">Te przykładowe konta dla tej różnicy.</span><span class="sxs-lookup"><span data-stu-id="95601-110">This example accounts for this difference.</span></span>

```csharp
XDocument co = XDocument.Load("CustomersOrders.xml");

// LINQ to XML query
XElement customer1 =
    (from el in co.Descendants("Customer")
     where (string)el.Attribute("CustomerID") ==
          (string)(co
              .Element("Root")
              .Element("Orders")
              .Elements("Order")
              .ToList()[11]
              .Element("CustomerID"))
    select el)
    .First();

// An alternate way to write the query that avoids creation
// of a System.Collections.Generic.List:
XElement customer2 =
    (from el in co.Descendants("Customer")
     where (string)el.Attribute("CustomerID") ==
          (string)(co
              .Element("Root")
              .Element("Orders")
              .Elements("Order")
              .Skip(11).First()
              .Element("CustomerID"))
    select el)
    .First();

// XPath expression
XElement customer3 = co.XPathSelectElement(
  ".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]");

if (customer1 == customer2 && customer1 == customer3)
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
Console.WriteLine(customer1);
```

```vb
Dim co As XDocument = XDocument.Load("CustomersOrders.xml")

' LINQ to XML query
Dim customer1 As XElement = ( _
    From el In co...<Customer> _
    Where el.@CustomerID = co.<Root>.<Orders>.<Order>. _
        ToList()(11).<CustomerID>(0).Value _
    Select el).First()

' An alternate way to write the query that avoids creation
' of a System.Collections.Generic.List:
Dim customer2 As XElement = ( _
    From el In co...<Customer> _
    Where el.@CustomerID = co.<Root>.<Orders>.<Order>. _
        Skip(11).First().<CustomerID>(0).Value _
    Select el).First()

' XPath expression
Dim customer3 As XElement = co.XPathSelectElement _
    (".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]")

If customer1 Is customer2 And customer1 Is customer3 Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
Console.WriteLine(customer1)
```

<span data-ttu-id="95601-111">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="95601-111">This example produces the following output:</span></span>

```output
Results are identical
<Customer CustomerID="HUNGC">
  <CompanyName>Hungry Coyote Import Store</CompanyName>
  <ContactName>Yoshi Latimer</ContactName>
  <ContactTitle>Sales Representative</ContactTitle>
  <Phone>(503) 555-6874</Phone>
  <Fax>(503) 555-2376</Fax>
  <FullAddress>
    <Address>City Center Plaza 516 Main St.</Address>
    <City>Elgin</City>
    <Region>OR</Region>
    <PostalCode>97827</PostalCode>
    <Country>USA</Country>
  </FullAddress>
</Customer>
```

## <a name="see-also"></a><span data-ttu-id="95601-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="95601-112">See also</span></span>

- [<span data-ttu-id="95601-113">LINQ to XML dla użytkowników XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95601-113">LINQ to XML for XPath Users (Visual Basic)</span></span>](./comparison-xpath-linq-xml.md)
