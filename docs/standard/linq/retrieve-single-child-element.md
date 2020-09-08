---
title: Jak pobrać pojedynczy element podrzędny LINQ to XML
description: Pobierz pierwszy element podrzędny o określonej nazwie. Można użyć XContainer. element w języku C# i notacji indeksatora Array w Visual Basic.
ms.date: 07/20/2015
ms.assetid: ce37db9e-76fa-46eb-b4cc-e8f32d22ad90
ms.openlocfilehash: e557e82e4e5891d6890a0efb4973796050b75349
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553654"
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml"></a>Pobieranie pojedynczego elementu podrzędnego (LINQ to XML)

W tym artykule wyjaśniono, jak pobrać pojedynczy element podrzędny, pierwszy element podrzędny, który ma określoną nazwę. W języku C# należy to zrobić przy użyciu <xref:System.Xml.Linq.XContainer.Element%2A> metody. W Visual Basic to zrobisz przy użyciu notacji Array indeksator.

## <a name="example-retrieve-the-first-element-that-has-a-specified-name"></a>Przykład: Pobierz pierwszy element, który ma określoną nazwę

Poniższy przykład pobiera pierwszy `DeliveryNotes` element z dokumentu XML w [przykładowym pliku XML: typowe zamówienie zakupu](sample-xml-file-typical-purchase-order.md).

```csharp
XElement po = XElement.Load("PurchaseOrder.xml");
XElement e = po.Element("DeliveryNotes");
Console.WriteLine(e);
```

```vb
Dim po As XElement = XElement.Load("PurchaseOrder.xml")
Dim e As XElement = po.<DeliveryNotes>(0)
Console.WriteLine(e)
```

Ten przykład generuje następujące wyniki:

```xml
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>
```

## <a name="example-retrieve-from-xml-thats-in-a-namespace"></a>Przykład: pobieranie z pliku XML, który znajduje się w przestrzeni nazw

Poniższy przykład działa tak samo jak powyżej, ale dla XML, który znajduje się w przestrzeni nazw. Używa [przykładowego pliku XML dokumentu XML: typowe zamówienie zakupu w przestrzeni nazw](sample-xml-file-typical-purchase-order-namespace.md). Aby uzyskać więcej informacji na temat przestrzeni nazw, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

```csharp
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");
XNamespace aw = "http://www.adventure-works.com";
XElement e = po.Element(aw + "DeliveryNotes");
Console.WriteLine(e);
```

```vb
Imports <xmlns:aw="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")
        Dim e As XElement = po.<aw:DeliveryNotes>(0)
        Console.WriteLine(e)
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```xml
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>
```

## <a name="see-also"></a>Zobacz też

- [Przegląd osi LINQ to XML](linq-xml-axes-overview.md)
