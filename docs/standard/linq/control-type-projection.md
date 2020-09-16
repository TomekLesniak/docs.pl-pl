---
title: Jak kontrolować typ projekcji — LINQ to XML
description: Można kontrolować typ kolekcji zwracanej przez zapytanie; nie musi to być interfejs IEnumerable z XElements.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: e4db6b7e-4cc9-4c8f-af85-94acf32aa348
ms.openlocfilehash: c92258fa9501aeeee46fe664cc4436f9349ff232
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558126"
---
# <a name="how-to-control-the-type-of-a-projection-linq-to-xml"></a><span data-ttu-id="f46dc-103">Jak kontrolować typ projekcji (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="f46dc-103">How to control the type of a projection (LINQ to XML)</span></span>

<span data-ttu-id="f46dc-104">*Projekcja* to proces filtrowania zestawu danych, zmiany jego kształtu i jego typu.</span><span class="sxs-lookup"><span data-stu-id="f46dc-104">*Projection* is the process of filtering a set of data, changing its shape and perhaps its type.</span></span> <span data-ttu-id="f46dc-105">Większość wyrażeń zapytania wykonuje projekcje.</span><span class="sxs-lookup"><span data-stu-id="f46dc-105">Most query expressions do projections.</span></span> <span data-ttu-id="f46dc-106">Większość wyrażeń zapytania w tej sekcji szacuje się na <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement> , ale można tworzyć Kolekcje innych typów.</span><span class="sxs-lookup"><span data-stu-id="f46dc-106">Most of the query expressions in this section evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, but you can create collections of other types.</span></span> <span data-ttu-id="f46dc-107">W tym artykule pokazano, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="f46dc-107">This article shows how to do this.</span></span>

## <a name="example-define-a-new-type-and-create-a-query-that-creates-an-ienumerable-of-that-type"></a><span data-ttu-id="f46dc-108">Przykład: Zdefiniuj nowy typ i Utwórz zapytanie, które tworzy interfejs IEnumerable tego typu</span><span class="sxs-lookup"><span data-stu-id="f46dc-108">Example: Define a new type and create a query that creates an IEnumerable of that type</span></span>

<span data-ttu-id="f46dc-109">W poniższym przykładzie zdefiniowano nowy typ, `Customer` a wyrażenie zapytania tworzy wystąpienie nowych `Customer` obiektów w `Select` klauzuli.</span><span class="sxs-lookup"><span data-stu-id="f46dc-109">The following example defines a new type, `Customer`, and the query expression instantiates new `Customer` objects in the `Select` clause.</span></span> <span data-ttu-id="f46dc-110">Powoduje to, że typ wyrażenia zapytania ma być <xref:System.Collections.Generic.IEnumerable%601> `Customer` .</span><span class="sxs-lookup"><span data-stu-id="f46dc-110">This causes the type of the query expression to be <xref:System.Collections.Generic.IEnumerable%601> of `Customer`.</span></span> <span data-ttu-id="f46dc-111">W przykładzie zastosowano [przykładowy plik XML dokumentu XML: klienci i zamówienia](sample-xml-file-customers-orders.md).</span><span class="sxs-lookup"><span data-stu-id="f46dc-111">The example uses XML document [Sample XML file: Customers and orders](sample-xml-file-customers-orders.md).</span></span>

```csharp
public class Customer
{
    private string customerID;
    public string CustomerID{ get{return customerID;} set{customerID = value;}}

    private string companyName;
    public string CompanyName{ get{return companyName;} set{companyName = value;}}

    private string contactName;
    public string ContactName { get{return contactName;} set{contactName = value;}}

    public Customer(string customerID, string companyName, string contactName)
    {
        CustomerID = customerID;
        CompanyName = companyName;
        ContactName = contactName;
    }

    public override string ToString()
    {
        return $"{this.customerID}:{this.companyName}:{this.contactName}";
    }
}

class Program
{
    static void Main(string[] args)
    {
        XElement custOrd = XElement.Load("CustomersOrders.xml");
        IEnumerable<Customer> custList =
            from el in custOrd.Element("Customers").Elements("Customer")
            select new Customer(
                (string)el.Attribute("CustomerID"),
                (string)el.Element("CompanyName"),
                (string)el.Element("ContactName")
            );
        foreach (Customer cust in custList)
            Console.WriteLine(cust);
    }


}
```

```vb
Public Class Customer
    Private customerIDValue As String
    Public Property CustomerID() As String
        Get
            Return customerIDValue
        End Get
        Set(ByVal value As String)
            customerIDValue = value
        End Set
    End Property

    Private companyNameValue As String
    Public Property CompanyName() As String
        Get
            Return companyNameValue
        End Get
        Set(ByVal value As String)
            companyNameValue = value
        End Set
    End Property

    Private contactNameValue As String
    Public Property ContactName() As String
        Get
            Return contactNameValue
        End Get
        Set(ByVal value As String)
            contactNameValue = value
        End Set
    End Property

    Public Sub New(ByVal customerID As String, _
                   ByVal companyName As String, _
                   ByVal contactName As String)
        CustomerIDValue = customerID
        CompanyNameValue = companyName
        ContactNameValue = contactName
    End Sub

    Public Overrides Function ToString() As String
        Return String.Format("{0}:{1}:{2}", Me.CustomerID, Me.CompanyName, Me.ContactName)
    End Function
End Class

Sub Main()
    Dim custOrd As XElement = XElement.Load("CustomersOrders.xml")
    Dim custList As IEnumerable(Of Customer) = _
        From el In custOrd.<Customers>.<Customer> _
        Select New Customer( _
            el.@<CustomerID>, _
            el.<CompanyName>.Value, _
            el.<ContactName>.Value _
        )
    For Each cust In custList
        Console.WriteLine(cust)
    Next
End Sub
```

<span data-ttu-id="f46dc-112">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="f46dc-112">This example produces the following output:</span></span>

```output
GREAL:Great Lakes Food Market:Howard Snyder
HUNGC:Hungry Coyote Import Store:Yoshi Latimer
LAZYK:Lazy K Kountry Store:John Steel
LETSS:Let's Stop N Shop:Jaime Yorres
```

## <a name="see-also"></a><span data-ttu-id="f46dc-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="f46dc-113">See also</span></span>

- <xref:System.Linq.Enumerable.Select%2A>
- [<span data-ttu-id="f46dc-114">Projekcje i przekształcenia (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f46dc-114">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](./work-dictionaries-linq-xml.md)
