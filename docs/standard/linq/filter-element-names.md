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
# <a name="how-to-filter-on-element-names-linq-to-xml"></a>Sposób filtrowania nazw elementów (LINQ to XML)

Po wywołaniu jednej z metod zwracanych przez <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement> , można filtrować według nazwy elementu.

## <a name="example-retrieve-descendants-filtered-to-a-specified-name"></a>Przykład: pobieranie elementów podrzędnych filtrowanych do określonej nazwy

Ten przykład pobiera kolekcję elementów podrzędnych, które są filtrowane, aby zawierały tylko elementy podrzędne o określonej nazwie.

Ten przykład używa [przykładowego pliku XML dokumentu XML: typowe zamówienie zakupu](sample-xml-file-typical-purchase-order.md).

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

Ten przykład generuje następujące wyniki:

```output
ProductName:Lawnmower
ProductName:Baby Monitor
```

Inne metody, które zwracają <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement> kolekcje, są zgodne z tym samym wzorcem. Ich podpisy są podobne do <xref:System.Xml.Linq.XContainer.Elements%2A> i <xref:System.Xml.Linq.XContainer.Descendants%2A> . Poniżej znajduje się kompletna lista metod, które mają podobne sygnatury metod:

- <xref:System.Xml.Linq.XNode.Ancestors%2A>
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>
- <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>
- <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>
- <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>

## <a name="example-retrieve-from-xml-thats-in-a-namespace"></a>Przykład: pobieranie z pliku XML, który znajduje się w przestrzeni nazw

W poniższym przykładzie pokazano to samo zapytanie dla kodu XML, który znajduje się w przestrzeni nazw. Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

W przykładzie zastosowano [przykładowy plik XML dokumentu XML: typowe zamówienie zakupu w przestrzeni nazw](sample-xml-file-typical-purchase-order-namespace.md).

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

Ten przykład generuje następujące wyniki:

```output
{http://www.adventure-works.com}ProductName:Lawnmower
{http://www.adventure-works.com}ProductName:Baby Monitor
```

## <a name="see-also"></a>Zobacz też

- [Przegląd osi LINQ to XML](linq-xml-axes-overview.md)
