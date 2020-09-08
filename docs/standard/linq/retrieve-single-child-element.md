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
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml"></a><span data-ttu-id="be7bc-104">Pobieranie pojedynczego elementu podrzędnego (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="be7bc-104">How to retrieve a single child element (LINQ to XML)</span></span>

<span data-ttu-id="be7bc-105">W tym artykule wyjaśniono, jak pobrać pojedynczy element podrzędny, pierwszy element podrzędny, który ma określoną nazwę.</span><span class="sxs-lookup"><span data-stu-id="be7bc-105">This article explains how to retrieve a single child element, the first child element that has a specified name.</span></span> <span data-ttu-id="be7bc-106">W języku C# należy to zrobić przy użyciu <xref:System.Xml.Linq.XContainer.Element%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="be7bc-106">In C# you do this with the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="be7bc-107">W Visual Basic to zrobisz przy użyciu notacji Array indeksator.</span><span class="sxs-lookup"><span data-stu-id="be7bc-107">In Visual Basic you do it with array indexer notation.</span></span>

## <a name="example-retrieve-the-first-element-that-has-a-specified-name"></a><span data-ttu-id="be7bc-108">Przykład: Pobierz pierwszy element, który ma określoną nazwę</span><span class="sxs-lookup"><span data-stu-id="be7bc-108">Example: Retrieve the first element that has a specified name</span></span>

<span data-ttu-id="be7bc-109">Poniższy przykład pobiera pierwszy `DeliveryNotes` element z dokumentu XML w [przykładowym pliku XML: typowe zamówienie zakupu](sample-xml-file-typical-purchase-order.md).</span><span class="sxs-lookup"><span data-stu-id="be7bc-109">The following example retrieves the first `DeliveryNotes` element from the XML document in [Sample XML file: Typical purchase order](sample-xml-file-typical-purchase-order.md).</span></span>

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

<span data-ttu-id="be7bc-110">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="be7bc-110">This example produces the following output:</span></span>

```xml
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>
```

## <a name="example-retrieve-from-xml-thats-in-a-namespace"></a><span data-ttu-id="be7bc-111">Przykład: pobieranie z pliku XML, który znajduje się w przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="be7bc-111">Example: Retrieve from XML that's in a namespace</span></span>

<span data-ttu-id="be7bc-112">Poniższy przykład działa tak samo jak powyżej, ale dla XML, który znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="be7bc-112">The following example does the same thing as the one above, but for XML that's in a namespace.</span></span> <span data-ttu-id="be7bc-113">Używa [przykładowego pliku XML dokumentu XML: typowe zamówienie zakupu w przestrzeni nazw](sample-xml-file-typical-purchase-order-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="be7bc-113">It uses the XML document [Sample XML file: Typical purchase order in a namespace](sample-xml-file-typical-purchase-order-namespace.md).</span></span> <span data-ttu-id="be7bc-114">Aby uzyskać więcej informacji na temat przestrzeni nazw, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).</span><span class="sxs-lookup"><span data-stu-id="be7bc-114">For more information about namespaces, see [Namespaces overview](namespaces-overview.md).</span></span>

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

<span data-ttu-id="be7bc-115">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="be7bc-115">This example produces the following output:</span></span>

```xml
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>
```

## <a name="see-also"></a><span data-ttu-id="be7bc-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="be7bc-116">See also</span></span>

- [<span data-ttu-id="be7bc-117">Przegląd osi LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="be7bc-117">LINQ to XML axes overview</span></span>](linq-xml-axes-overview.md)
