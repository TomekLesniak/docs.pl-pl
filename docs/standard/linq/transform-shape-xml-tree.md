---
title: Jak przekształcić kształt drzewa XML — LINQ to XML
description: Aby zmienić kształt dokumentu XML, można użyć konstrukcji funkcjonalnej. to jest, aby zachować dane, ale zmieniać takie elementy jak nazwy elementów, nazwy atrybutów i hierarchie.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 93c5d426-dea2-4709-a991-60204de42e8f
ms.openlocfilehash: 7f78cb2542357be674d771f93825b7f4a56abea0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554507"
---
# <a name="how-to-transform-the-shape-of-an-xml-tree-linq-to-xml"></a>Jak przekształcić kształt drzewa XML (LINQ to XML)

*Kształt* dokumentu XML odwołuje się do jego nazw elementów, nazw atrybutów i cech hierarchii.

Czasami trzeba będzie zmienić kształt dokumentu XML. Na przykład może być konieczne wysłanie istniejącego dokumentu XML do innego systemu, który wymaga innych nazw elementów i atrybutów. Możesz przejść przez dokument, usunąć i zmienić nazwy elementów zgodnie z potrzebami, ale użycie konstrukcji funkcjonalnej skutkuje bardziej czytelnym i możliwym do utrzymania kodem. Aby uzyskać więcej informacji na temat konstrukcji funkcjonalnej, zobacz [funkcjonalne konstruowanie](functional-construction.md).

Pierwszy przykład w tym artykule zmienia organizację dokumentu XML. Przenosi elementy złożone z jednej lokalizacji w drzewie do innej.

Drugi przykład tworzy dokument XML, którego kształt różni się od dokumentu źródłowego. Pomija niektóre elementy, zmienia nazwy innych, a zmiany wielkości liter w nazwach elementów.

## <a name="example-use-embedded-query-expressions-to-change-the-shape-of-an-xml-tree"></a>Przykład: Użyj osadzonych wyrażeń zapytania, aby zmienić kształt drzewa XML

Poniższy przykład zmienia kształt pliku XML przy użyciu osadzonych wyrażeń zapytań.

Źródłowy dokument XML dla tego przykładu [przykładowy plik XML: klienci i zamówienia](sample-xml-file-customers-orders.md), zawierający element, `Customers` `Root` który zawiera wszystkich klientów. Zawiera również `Orders` element w obszarze `Root` elementu, który zawiera wszystkie zamówienia. Przykład tworzy nowe drzewo XML, w którym zamówienia dla każdego klienta są zawarte w `Orders` elemencie w `Customer` elemencie. Oryginalny dokument zawiera również `CustomerID` element w `Order` elemencie; ten element zostanie pominięty w nowym drzewie.

```csharp
XElement co = XElement.Load("CustomersOrders.xml");
XElement newCustOrd =
    new XElement("Root",
        from cust in co.Element("Customers").Elements("Customer")
        select new XElement("Customer",
            cust.Attributes(),
            cust.Elements(),
            new XElement("Orders",
                from ord in co.Element("Orders").Elements("Order")
                where (string)ord.Element("CustomerID") == (string)cust.Attribute("CustomerID")
                select new XElement("Order",
                    ord.Attributes(),
                    ord.Element("EmployeeID"),
                    ord.Element("OrderDate"),
                    ord.Element("RequiredDate"),
                    ord.Element("ShipInfo")
                )
            )
        )
    );
Console.WriteLine(newCustOrd);
```

 ```vb
Dim co As XElement = XElement.Load("CustomersOrders.xml")
Dim newCustOrd = _
    <Root>
        <%= From cust In co.<Customers>.<Customer> _
            Select _
            <Customer>
                <%= cust.Attributes() %>
                <%= cust.Elements() %>
                <Orders>
                    <%= From ord In co.<Orders>.<Order> _
                        Where ord.<CustomerID>.Value = cust.@CustomerID _
                        Select _
                        <Order>
                            <%= ord.Attributes() %>
                            <%= ord.<EmployeeID> %>
                            <%= ord.<OrderDate> %>
                            <%= ord.<RequiredDate> %>
                            <%= ord.<ShipInfo> %>
                        </Order> _
                    %>
                </Orders>
            </Customer> _
        %>
    </Root>
Console.WriteLine(newCustOrd)
```

Ten przykład generuje następujące wyniki:

```xml
<Root>
  <Customer CustomerID="GREAL">
    <CompanyName>Great Lakes Food Market</CompanyName>
    <ContactName>Howard Snyder</ContactName>
    <ContactTitle>Marketing Manager</ContactTitle>
    <Phone>(503) 555-7555</Phone>
    <FullAddress>
      <Address>2732 Baker Blvd.</Address>
      <City>Eugene</City>
      <Region>OR</Region>
      <PostalCode>97403</PostalCode>
      <Country>USA</Country>
    </FullAddress>
    <Orders />
  </Customer>
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
    <Orders />
  </Customer>
  ...
</Root>
```

## <a name="example-create-a-document-whose-shape-differs-from-that-of-the-source-document"></a>Przykład: Utwórz dokument, którego kształt różni się od dokumentu źródłowego

Ten przykład zmienia nazwę niektórych elementów i konwertuje niektóre atrybuty do elementów. Wywołuje `ConvertAddress` , która zwraca listę <xref:System.Xml.Linq.XElement> obiektów. Argument metody jest zapytanie, które określa `Address` element złożony, gdzie `Type` atrybut ma wartość `"Shipping"` . W przykładzie zastosowano [przykładowy plik XML dokumentu XML: typowe zamówienie zakupu](sample-xml-file-typical-purchase-order.md).

```csharp
static IEnumerable<XElement> ConvertAddress(XElement add)
{
    List<XElement> fragment = new List<XElement>() {
        new XElement("NAME", (string)add.Element("Name")),
        new XElement("STREET", (string)add.Element("Street")),
        new XElement("CITY", (string)add.Element("City")),
        new XElement("ST", (string)add.Element("State")),
        new XElement("POSTALCODE", (string)add.Element("Zip")),
        new XElement("COUNTRY", (string)add.Element("Country"))
    };
    return fragment;
}

static void Main(string[] args)
{
    XElement po = XElement.Load("PurchaseOrder.xml");
    XElement newPo = new XElement("PO",
        new XElement("ID", (string)po.Attribute("PurchaseOrderNumber")),
        new XElement("DATE", (DateTime)po.Attribute("OrderDate")),
        ConvertAddress(
            (from el in po.Elements("Address")
            where (string)el.Attribute("Type") == "Shipping"
            select el)
            .First()
        )
    );
    Console.WriteLine(newPo);
}
```

```vb
Function ConvertAddress(ByVal add As XElement) As IEnumerable(Of XElement)
    Dim fragment = New List(Of XElement)
    fragment.Add(<NAME><%= add.<Name>.Value %></NAME>)
    fragment.Add(<STREET><%= add.<Street>.Value %></STREET>)
    fragment.Add(<CITY><%= add.<City>.Value %></CITY>)
    fragment.Add(<ST><%= add.<State>.Value %></ST>)
    fragment.Add(<POSTALCODE><%= add.<Zip>.Value %></POSTALCODE>)
    fragment.Add(<COUNTRY><%= add.<Country>.Value %></COUNTRY>)
    Return fragment
End Function

Sub Main()
    Dim po As XElement = XElement.Load("PurchaseOrder.xml")
    Dim newPo As XElement = _
        <PO>
            <ID><%= po.@PurchaseOrderNumber %></ID>
            <DATE><%= CDate(po.@OrderDate) %></DATE>
            <%= _
                ConvertAddress( _
                (From el In po.<Address> _
                Where el.@Type = "Shipping" _
                Select el) _
                .First() _
                ) _
            %>
        </PO>
    Console.WriteLine(newPo)
End Sub
```

Ten przykład generuje następujące wyniki:

```xml
<PO>
  <ID>99503</ID>
  <DATE>1999-10-20T00:00:00</DATE>
  <NAME>Ellen Adams</NAME>
  <STREET>123 Maple Street</STREET>
  <CITY>Mill Valley</CITY>
  <ST>CA</ST>
  <POSTALCODE>10999</POSTALCODE>
  <COUNTRY>USA</COUNTRY>
</PO>
```

## <a name="see-also"></a>Zobacz także

- [Projekcje i przekształcenia (LINQ to XML) (Visual Basic)](./work-dictionaries-linq-xml.md)
