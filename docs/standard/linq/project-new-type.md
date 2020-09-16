---
title: Jak zaprojektować nowy typ LINQ to XML
description: Zapytanie może zwracać interfejs IEnumerable typu innego niż wspólny. W tym artykule pokazano, jak w przykładzie.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: a0ce8d9e5199b290dc759c191c4db7a37ddc9a55
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547537"
---
# <a name="how-to-project-a-new-type-linq-to-xml"></a>Projektowanie nowego typu (LINQ to XML)

W innych przykładach w tej sekcji przedstawiono zapytania, które zwracają wyniki w zakresie od, do <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement> <xref:System.Collections.Generic.IEnumerable%601> `string` i <xref:System.Collections.Generic.IEnumerable%601> `int` . Są to typowe typy wyników, ale nie są one odpowiednie dla każdego scenariusza. W wielu przypadkach zapytania będą zwracały <xref:System.Collections.Generic.IEnumerable%601> Inne typy.

## <a name="example-define-a-new-type-and-have-the-select-statement-create-an-instance-of-the-type"></a>Przykład: Zdefiniuj nowy typ i `select` Utwórz wystąpienie typu

Ten przykład pokazuje, jak utworzyć wystąpienie obiektów w `select` klauzuli. Kod wywołuje najpierw konstruktora w celu zdefiniowania nowej klasy, a następnie modyfikuje `select` instrukcję tak, aby wyrażenie było nowym wystąpieniem nowej klasy. W przykładzie zastosowano [przykładowy plik XML dokumentu XML: typowe zamówienie zakupu](sample-xml-file-typical-purchase-order.md).

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

W tym przykładzie użyto <xref:System.Xml.Linq.XContainer.Element%2A> metody, która została wprowadzona w artykule [jak pobrać pojedynczy element podrzędny](retrieve-single-child-element.md) . Używa również rzutowania do pobrania wartości elementów, które są zwracane przez <xref:System.Xml.Linq.XContainer.Element%2A> metodę.

Ten przykład generuje następujące wyniki:

```output
Lawnmower:1
Baby Monitor:2
```

## <a name="see-also"></a>Zobacz także

- [Projekcje i przekształcenia (LINQ to XML) (Visual Basic)](./work-dictionaries-linq-xml.md)
