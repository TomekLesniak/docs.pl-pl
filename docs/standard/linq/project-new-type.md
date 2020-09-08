---
title: Jak zaprojektować nowy typ LINQ to XML
description: Zapytanie może zwracać interfejs IEnumerable typu innego niż wspólny. W tym artykule pokazano, jak w przykładzie.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: 15eabf37e23363894ec1ab72e6df6dbe1fd974db
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553264"
---
# <a name="how-to-project-a-new-type-linq-to-xml"></a><span data-ttu-id="439d0-104">Projektowanie nowego typu (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="439d0-104">How to project a new type (LINQ to XML)</span></span>

<span data-ttu-id="439d0-105">W innych przykładach w tej sekcji przedstawiono zapytania, które zwracają wyniki w zakresie od, do <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement> <xref:System.Collections.Generic.IEnumerable%601> `string` i <xref:System.Collections.Generic.IEnumerable%601> `int` .</span><span class="sxs-lookup"><span data-stu-id="439d0-105">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="439d0-106">Są to typowe typy wyników, ale nie są one odpowiednie dla każdego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="439d0-106">These are common result types, but they're not appropriate for every scenario.</span></span> <span data-ttu-id="439d0-107">W wielu przypadkach zapytania będą zwracały <xref:System.Collections.Generic.IEnumerable%601> Inne typy.</span><span class="sxs-lookup"><span data-stu-id="439d0-107">In many cases, you'll want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>

## <a name="example-define-a-new-type-and-have-the-select-statement-create-an-instance-of-the-type"></a><span data-ttu-id="439d0-108">Przykład: Zdefiniuj nowy typ i `select` Utwórz wystąpienie typu</span><span class="sxs-lookup"><span data-stu-id="439d0-108">Example: Define a new type and have the `select` statement create an instance of the type</span></span>

<span data-ttu-id="439d0-109">Ten przykład pokazuje, jak utworzyć wystąpienie obiektów w `select` klauzuli.</span><span class="sxs-lookup"><span data-stu-id="439d0-109">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="439d0-110">Kod wywołuje najpierw konstruktora w celu zdefiniowania nowej klasy, a następnie modyfikuje `select` instrukcję tak, aby wyrażenie było nowym wystąpieniem nowej klasy.</span><span class="sxs-lookup"><span data-stu-id="439d0-110">The code first invokes a constructor to define a new class, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span> <span data-ttu-id="439d0-111">W przykładzie zastosowano [przykładowy plik XML dokumentu XML: typowe zamówienie zakupu](sample-xml-file-typical-purchase-order.md).</span><span class="sxs-lookup"><span data-stu-id="439d0-111">The example uses XML document [Sample XML file: Typical purchase order](sample-xml-file-typical-purchase-order.md).</span></span>

```csharp
class NameQty
{
    public string name;
    public int qty;
    public NameQty(string n, int q)
    {
        name = n;
        qty = q;
    }
};

class Program {
    public static void Main()
    {
        XElement po = XElement.Load("PurchaseOrder.xml");

        IEnumerable<NameQty> nqList =
            from n in po.Descendants("Item")
            select new NameQty(
                    (string)n.Element("ProductName"),
                    (int)n.Element("Quantity")
                );

        foreach (NameQty n in nqList)
            Console.WriteLine(n.name + ":" + n.qty);
    }
}
```

```vb
Public Class NameQty
    Public name As String
    Public qty As Integer
    Public Sub New(ByVal n As String, ByVal q As Integer)
        name = n
        qty = q
    End Sub
End Class

Public Class Program
    Shared Sub Main()
        Dim po As XElement = XElement.Load("PurchaseOrder.xml")

        Dim nqList As IEnumerable(Of NameQty) = _
            From n In po...<Item> _
            Select New NameQty( _
                n.<ProductName>.Value, CInt(n.<Quantity>.Value))

        For Each n As NameQty In nqList
            Console.WriteLine(n.name & ":" & n.qty)
        Next
    End Sub
End Class
```

<span data-ttu-id="439d0-112">W tym przykładzie użyto <xref:System.Xml.Linq.XContainer.Element%2A> metody, która została wprowadzona w artykule [jak pobrać pojedynczy element podrzędny](retrieve-single-child-element.md) .</span><span class="sxs-lookup"><span data-stu-id="439d0-112">This example uses the <xref:System.Xml.Linq.XContainer.Element%2A> method that was introduced in the [How to retrieve a single child element](retrieve-single-child-element.md) article.</span></span> <span data-ttu-id="439d0-113">Używa również rzutowania do pobrania wartości elementów, które są zwracane przez <xref:System.Xml.Linq.XContainer.Element%2A> metodę.</span><span class="sxs-lookup"><span data-stu-id="439d0-113">It also uses casts to retrieve the values of the elements that are returned by the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>

<span data-ttu-id="439d0-114">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="439d0-114">This example produces the following output:</span></span>

```output
Lawnmower:1
Baby Monitor:2
```

## <a name="see-also"></a><span data-ttu-id="439d0-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="439d0-115">See also</span></span>

- [<span data-ttu-id="439d0-116">Projekcje i przekształcenia (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="439d0-116">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
