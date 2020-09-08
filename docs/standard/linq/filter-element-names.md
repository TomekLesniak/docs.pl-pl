---
title: Jak filtrować nazwy elementów — LINQ to XML
description: Dowiedz się, jak filtrować według nazwy elementu po wywołaniu metody, która zwraca interfejs IEnumerable z XElement.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 1849fb03-f075-421f-863c-e8fb32773cdf
ms.openlocfilehash: 1f831fe0008c94b3956e93f3ced7176d8c0bf34e
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552918"
---
# <a name="how-to-filter-on-element-names-linq-to-xml"></a><span data-ttu-id="15049-103">Sposób filtrowania nazw elementów (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="15049-103">How to filter on element names (LINQ to XML)</span></span>

<span data-ttu-id="15049-104">Po wywołaniu jednej z metod zwracanych przez <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement> , można filtrować według nazwy elementu.</span><span class="sxs-lookup"><span data-stu-id="15049-104">When you call one of the methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, you can filter on the element name.</span></span>

## <a name="example-retrieve-descendants-filtered-to-a-specified-name"></a><span data-ttu-id="15049-105">Przykład: pobieranie elementów podrzędnych filtrowanych do określonej nazwy</span><span class="sxs-lookup"><span data-stu-id="15049-105">Example: Retrieve descendants filtered to a specified name</span></span>

<span data-ttu-id="15049-106">Ten przykład pobiera kolekcję elementów podrzędnych, które są filtrowane, aby zawierały tylko elementy podrzędne o określonej nazwie.</span><span class="sxs-lookup"><span data-stu-id="15049-106">This example retrieves a collection of descendants that's filtered to contain only descendants with the specified name.</span></span>

<span data-ttu-id="15049-107">Ten przykład używa [przykładowego pliku XML dokumentu XML: typowe zamówienie zakupu](sample-xml-file-typical-purchase-order.md).</span><span class="sxs-lookup"><span data-stu-id="15049-107">This example uses XML document [Sample XML file: Typical purchase order](sample-xml-file-typical-purchase-order.md).</span></span>

```csharp
XElement po = XElement.Load("PurchaseOrder.xml");
IEnumerable<XElement> items =
    from el in po.Descendants("ProductName")
    select el;
foreach(XElement prdName in items)
    Console.WriteLine(prdName.Name + ":" + (string) prdName);
```

```vb
Dim po As XElement = XElement.Load("PurchaseOrder.xml")
Dim items As IEnumerable(Of XElement) = _
    From el In po...<ProductName> _
    Select el
For Each prdName As XElement In items
    Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)
Next
```

<span data-ttu-id="15049-108">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="15049-108">This example produces the following output:</span></span>

```output
ProductName:Lawnmower
ProductName:Baby Monitor
```

<span data-ttu-id="15049-109">Inne metody, które zwracają <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement> kolekcje, są zgodne z tym samym wzorcem.</span><span class="sxs-lookup"><span data-stu-id="15049-109">The other methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> collections follow the same pattern.</span></span> <span data-ttu-id="15049-110">Ich podpisy są podobne do <xref:System.Xml.Linq.XContainer.Elements%2A> i <xref:System.Xml.Linq.XContainer.Descendants%2A> .</span><span class="sxs-lookup"><span data-stu-id="15049-110">Their signatures are similar to <xref:System.Xml.Linq.XContainer.Elements%2A> and <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span></span> <span data-ttu-id="15049-111">Poniżej znajduje się kompletna lista metod, które mają podobne sygnatury metod:</span><span class="sxs-lookup"><span data-stu-id="15049-111">The following is the complete list of methods that have similar method signatures:</span></span>

- <xref:System.Xml.Linq.XNode.Ancestors%2A>
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>
- <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>
- <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>
- <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>

## <a name="example-retrieve-from-xml-thats-in-a-namespace"></a><span data-ttu-id="15049-112">Przykład: pobieranie z pliku XML, który znajduje się w przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="15049-112">Example: Retrieve from XML that's in a namespace</span></span>

<span data-ttu-id="15049-113">W poniższym przykładzie pokazano to samo zapytanie dla kodu XML, który znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="15049-113">The following example shows the same query for XML that's in a namespace.</span></span> <span data-ttu-id="15049-114">Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).</span><span class="sxs-lookup"><span data-stu-id="15049-114">For more information, see [Namespaces overview](namespaces-overview.md).</span></span>

<span data-ttu-id="15049-115">W przykładzie zastosowano [przykładowy plik XML dokumentu XML: typowe zamówienie zakupu w przestrzeni nazw](sample-xml-file-typical-purchase-order-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="15049-115">The example uses XML document [Sample XML file: Typical purchase order in a namespace](sample-xml-file-typical-purchase-order-namespace.md).</span></span>

```csharp
XNamespace aw = "http://www.adventure-works.com";
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");
IEnumerable<XElement> items =
    from el in po.Descendants(aw + "ProductName")
    select el;
foreach (XElement prdName in items)
    Console.WriteLine(prdName.Name + ":" + (string)prdName);
```

```vb
Imports <xmlns:aw="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")
        Dim items As IEnumerable(Of XElement) = _
            From el In po...<aw:ProductName> _
            Select el
        For Each prdName As XElement In items
            Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)
        Next
    End Sub
End Module
```

<span data-ttu-id="15049-116">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="15049-116">This example produces the following output:</span></span>

```output
{http://www.adventure-works.com}ProductName:Lawnmower
{http://www.adventure-works.com}ProductName:Baby Monitor
```

## <a name="see-also"></a><span data-ttu-id="15049-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="15049-117">See also</span></span>

- [<span data-ttu-id="15049-118">Przegląd osi LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="15049-118">LINQ to XML axes overview</span></span>](linq-xml-axes-overview.md)
