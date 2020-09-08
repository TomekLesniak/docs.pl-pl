---
title: Jak sprzęgać dwie kolekcje — LINQ to XML
description: Plik XSD może ustanowić relacje w pliku XML, aby umożliwić łączenie elementów w celu utworzenia nowych typów elementów. Ten artykuł zawiera przykład dla języka C# i Visual Basic, który sprzęga elementy i tworzy nowy dokument XML.
ms.date: 07/20/2015
ms.assetid: 7b817ede-911a-4cff-9dd3-639c3fc228c9
dev_langs:
- csharp
- vb
ms.openlocfilehash: 2ab74f861cfd046e202a861378b8fd8792c7bac4
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553379"
---
# <a name="how-to-join-two-collections-linq-to-xml"></a>Łączenie dwóch kolekcji (LINQ to XML)

Plik XSD może ustanowić relacje w pliku XML, aby umożliwić łączenie elementów w celu utworzenia nowych typów elementów. Ten artykuł zawiera przykład dla języka C# i Visual Basic, który sprzęga elementy i tworzy nowy dokument XML.

Element lub atrybut w dokumencie XML czasami może odwoływać się do innego elementu lub atrybutu. [Przykładowy plik XML dokumentu XML: klienci i zamówienia](sample-xml-file-customers-orders.md) zawierają listę klientów i listę zamówień. Każdy `Customer` element ma `CustomerID` atrybut, a każdy `Order` element zawiera `CustomerID` element. `CustomerID`Wartość elementu w `Order` elemencie odwołuje się do `Customer` elementu, który ma pasującą `CustomerID` wartość atrybutu.

[Przykładowy plik XSD artykułu: klienci i zamówienia](sample-xsd-file-customers-orders.md) zawierają XSD, których można użyć do walidacji `Customers and orders` dokumentu. Używa `xs:key` i `xs:keyref` funkcji XSD, aby określić, że `CustomerID` atrybut `Customer` elementu jest kluczem i aby ustanowić relację między kluczem i `CustomerID` elementem  `Order` elementów.

Za pomocą LINQ to XML można wykorzystać tę relację przy użyciu `join` klauzuli, aby dołączyć informacje o kliencie do zamówienia informacji.

Aby uzyskać bardziej szczegółowe informacje na temat `join` , zobacz [operacje join (C#)](../../csharp/programming-guide/concepts/linq/join-operations.md) i [operacje join (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/join-operations.md).
> [!NOTE]
> Sprzężenia są wykonywane przy użyciu wyszukiwania liniowego. Brak indeksów do zwiększenia wydajności wyszukiwania.

## <a name="example-create-a-new-xml-document-that-has-customer-and-order-elements-joined"></a>Przykład: Utwórz nowy dokument XML, który zawiera `Customer` i `Order` elementy dołączone

Poniższy przykład generuje nowy dokument XML, który sprzęga `Customer` elementy [przykładowego pliku XML: klienci i zamówienia](sample-xml-file-customers-orders.md) do `Order` elementów i zawiera `CompanyName` element w zamówieniach.

Przed wykonaniem zapytania, przykład sprawdza, czy dokument jest zgodny ze schematem w [przykładowym pliku XSD: klienci i zamówienia](sample-xsd-file-customers-orders.md). Dzięki temu Klauzula join będzie działała.

Zapytanie wybiera tylko zamówienia dla klientów o `CustomerID` większej niż "K". Projekt IT `Order` zawiera nowe elementy, które zawierają informacje o klientach w ramach poszczególnych zamówień.

```csharp
XmlSchemaSet schemas = new XmlSchemaSet();
schemas.Add("", "CustomersOrders.xsd");

Console.Write("Attempting to validate, ");
XDocument custOrdDoc = XDocument.Load("CustomersOrders.xml");

bool errors = false;
custOrdDoc.Validate(schemas, (o, e) =>
                     {
                         Console.WriteLine("{0}", e.Message);
                         errors = true;
                     });
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");

if (!errors)
{
    // Join customers and orders, and create a new XML document with
    // a different shape.

    // The new document contains orders only for customers with a
    // CustomerID > 'K'
    XElement custOrd = custOrdDoc.Element("Root");
    XElement newCustOrd = new XElement("Root",
        from c in custOrd.Element("Customers").Elements("Customer")
        join o in custOrd.Element("Orders").Elements("Order")
                   on (string)c.Attribute("CustomerID") equals
                      (string)o.Element("CustomerID")
        where ((string)c.Attribute("CustomerID")).CompareTo("K") > 0
        select new XElement("Order",
            new XElement("CustomerID", (string)c.Attribute("CustomerID")),
            new XElement("CompanyName", (string)c.Element("CompanyName")),
            new XElement("ContactName", (string)c.Element("ContactName")),
            new XElement("EmployeeID", (string)o.Element("EmployeeID")),
            new XElement("OrderDate", (DateTime)o.Element("OrderDate"))
        )
    );
    Console.WriteLine(newCustOrd);
}
```

```vb
Public Class Program
    Public Shared errors As Boolean = False

    Public Shared Function LamValidEvent(ByVal o As Object, _
                 ByVal e As ValidationEventArgs) As Boolean
        Console.WriteLine("{0}", e.Message)
        errors = True
    End Function

    Shared Sub Main()
        Dim schemas As New XmlSchemaSet()
        schemas.Add("", "CustomersOrders.xsd")

        Console.Write("Attempting to validate, ")
        Dim custOrdDoc As XDocument = XDocument.Load("CustomersOrders.xml")

        custOrdDoc.Validate(schemas, Function(o, e) LamValidEvent(0, e))
        If errors Then
            Console.WriteLine("custOrdDoc did not validate")
        Else
            Console.WriteLine("custOrdDoc validated")
        End If

        If Not errors Then
            'Join customers and orders, and create a new XML document with
            ' a different shape.
            'The new document contains orders only for customers with a
            ' CustomerID > 'K'.
            Dim custOrd As XElement = custOrdDoc.<Root>.FirstOrDefault
            Dim newCustOrd As XElement = _
                <Root>
                    <%= From c In custOrd.<Customers>.<Customer> _
                        Join o In custOrd.<Orders>.<Order> _
                        On c.@CustomerID Equals o.<CustomerID>.Value _
                        Where c.@CustomerID.CompareTo("K") > 0 _
                        Select _
                        <Order>
                            <CustomerID><%= c.@CustomerID %></CustomerID>
                            <%= c.<CompanyName> %>
                            <%= c.<ContactName> %>
                            <%= o.<EmployeeID> %>
                            <%= o.<OrderDate> %>
                        </Order> _
                    %>
                </Root>
            Console.WriteLine(newCustOrd)
        End If
    End Sub
End Class
```

Ten przykład generuje następujące wyniki:

```output
Attempting to validate, custOrdDoc validated
<Root>
  <Order>
    <CustomerID>LAZYK</CustomerID>
    <CompanyName>Lazy K Kountry Store</CompanyName>
    <ContactName>John Steel</ContactName>
    <EmployeeID>1</EmployeeID>
    <OrderDate>1997-03-21T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LAZYK</CustomerID>
    <CompanyName>Lazy K Kountry Store</CompanyName>
    <ContactName>John Steel</ContactName>
    <EmployeeID>8</EmployeeID>
    <OrderDate>1997-05-22T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>1</EmployeeID>
    <OrderDate>1997-06-25T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>8</EmployeeID>
    <OrderDate>1997-10-27T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>6</EmployeeID>
    <OrderDate>1997-11-10T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>4</EmployeeID>
    <OrderDate>1998-02-12T00:00:00</OrderDate>
  </Order>
</Root>
```
