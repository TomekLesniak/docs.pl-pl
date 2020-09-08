---
title: Jak przekształcić kształt drzewa XML — LINQ to XML
description: Aby zmienić kształt dokumentu XML, można użyć konstrukcji funkcjonalnej. to jest, aby zachować dane, ale zmieniać takie elementy jak nazwy elementów, nazwy atrybutów i hierarchie.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 93c5d426-dea2-4709-a991-60204de42e8f
ms.openlocfilehash: 6b4127571d5a6a9fa8e92079424dd19eaf5a2f29
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553140"
---
# <a name="how-to-transform-the-shape-of-an-xml-tree-linq-to-xml"></a><span data-ttu-id="b3a9b-103">Jak przekształcić kształt drzewa XML (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="b3a9b-103">How to transform the shape of an XML tree (LINQ to XML)</span></span>

<span data-ttu-id="b3a9b-104">*Kształt* dokumentu XML odwołuje się do jego nazw elementów, nazw atrybutów i cech hierarchii.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-104">The *shape* of an XML document refers to its element names, attribute names, and the characteristics of its hierarchy.</span></span>

<span data-ttu-id="b3a9b-105">Czasami trzeba będzie zmienić kształt dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-105">Sometimes you will have to change the shape of an XML document.</span></span> <span data-ttu-id="b3a9b-106">Na przykład może być konieczne wysłanie istniejącego dokumentu XML do innego systemu, który wymaga innych nazw elementów i atrybutów.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-106">For example, you might have to send an existing XML document to another system that requires different element and attribute names.</span></span> <span data-ttu-id="b3a9b-107">Możesz przejść przez dokument, usunąć i zmienić nazwy elementów zgodnie z potrzebami, ale użycie konstrukcji funkcjonalnej skutkuje bardziej czytelnym i możliwym do utrzymania kodem.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-107">You could go through the document, deleting and renaming elements as required, but using functional construction results in more readable and maintainable code.</span></span> <span data-ttu-id="b3a9b-108">Aby uzyskać więcej informacji na temat konstrukcji funkcjonalnej, zobacz [funkcjonalne konstruowanie](functional-construction.md).</span><span class="sxs-lookup"><span data-stu-id="b3a9b-108">For more information about functional construction, see [Functional construction](functional-construction.md).</span></span>

<span data-ttu-id="b3a9b-109">Pierwszy przykład w tym artykule zmienia organizację dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-109">The first example in this article changes the organization of an XML document.</span></span> <span data-ttu-id="b3a9b-110">Przenosi elementy złożone z jednej lokalizacji w drzewie do innej.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-110">It moves complex elements from one location in the tree to another.</span></span>

<span data-ttu-id="b3a9b-111">Drugi przykład tworzy dokument XML, którego kształt różni się od dokumentu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-111">The second example creates an XML document whose shape differs from that of the source document.</span></span> <span data-ttu-id="b3a9b-112">Pomija niektóre elementy, zmienia nazwy innych, a zmiany wielkości liter w nazwach elementów.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-112">It omits some elements, renames others, and changes the casing of the element names.</span></span>

## <a name="example-use-embedded-query-expressions-to-change-the-shape-of-an-xml-tree"></a><span data-ttu-id="b3a9b-113">Przykład: Użyj osadzonych wyrażeń zapytania, aby zmienić kształt drzewa XML</span><span class="sxs-lookup"><span data-stu-id="b3a9b-113">Example: Use embedded query expressions to change the shape of an XML tree</span></span>

<span data-ttu-id="b3a9b-114">Poniższy przykład zmienia kształt pliku XML przy użyciu osadzonych wyrażeń zapytań.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-114">The following example changes the shape of an XML file using embedded query expressions.</span></span>

<span data-ttu-id="b3a9b-115">Źródłowy dokument XML dla tego przykładu [przykładowy plik XML: klienci i zamówienia](sample-xml-file-customers-orders.md), zawierający element, `Customers` `Root` który zawiera wszystkich klientów.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-115">The source XML document for this example, [Sample XML file: Customers and orders](sample-xml-file-customers-orders.md), contains a `Customers` element under the `Root` element that contains all customers.</span></span> <span data-ttu-id="b3a9b-116">Zawiera również `Orders` element w obszarze `Root` elementu, który zawiera wszystkie zamówienia.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-116">It also contains an `Orders` element under the `Root` element that contains all orders.</span></span> <span data-ttu-id="b3a9b-117">Przykład tworzy nowe drzewo XML, w którym zamówienia dla każdego klienta są zawarte w `Orders` elemencie w `Customer` elemencie.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-117">The example creates a new XML tree in which the orders for each customer are contained in an `Orders` element within the `Customer` element.</span></span> <span data-ttu-id="b3a9b-118">Oryginalny dokument zawiera również `CustomerID` element w `Order` elemencie; ten element zostanie pominięty w nowym drzewie.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-118">The original document also contains a `CustomerID` element in the `Order` element; this element is omitted from the new tree.</span></span>

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

<span data-ttu-id="b3a9b-119">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="b3a9b-119">This example produces the following output:</span></span>

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

## <a name="example-create-a-document-whose-shape-differs-from-that-of-the-source-document"></a><span data-ttu-id="b3a9b-120">Przykład: Utwórz dokument, którego kształt różni się od dokumentu źródłowego</span><span class="sxs-lookup"><span data-stu-id="b3a9b-120">Example: Create a document whose shape differs from that of the source document</span></span>

<span data-ttu-id="b3a9b-121">Ten przykład zmienia nazwę niektórych elementów i konwertuje niektóre atrybuty do elementów.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-121">This example renames some elements and converts some attributes to elements.</span></span> <span data-ttu-id="b3a9b-122">Wywołuje `ConvertAddress` , która zwraca listę <xref:System.Xml.Linq.XElement> obiektów.</span><span class="sxs-lookup"><span data-stu-id="b3a9b-122">It calls `ConvertAddress`, which returns a list of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="b3a9b-123">Argument metody jest zapytanie, które określa `Address` element złożony, gdzie `Type` atrybut ma wartość `"Shipping"` .</span><span class="sxs-lookup"><span data-stu-id="b3a9b-123">The argument to the method is a query that determines the `Address` complex element where the `Type` attribute has a value of `"Shipping"`.</span></span> <span data-ttu-id="b3a9b-124">W przykładzie zastosowano [przykładowy plik XML dokumentu XML: typowe zamówienie zakupu](sample-xml-file-typical-purchase-order.md).</span><span class="sxs-lookup"><span data-stu-id="b3a9b-124">The example uses XML document [Sample XML file: Typical purchase order](sample-xml-file-typical-purchase-order.md).</span></span>

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

<span data-ttu-id="b3a9b-125">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="b3a9b-125">This example produces the following output:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b3a9b-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b3a9b-126">See also</span></span>

- [<span data-ttu-id="b3a9b-127">Projekcje i przekształcenia (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3a9b-127">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
