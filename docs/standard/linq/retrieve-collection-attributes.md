---
title: Jak pobrać kolekcję atrybutów — LINQ to XML
description: Dowiedz się, jak za pomocą metody XElement. Attributes pobrać atrybuty elementu.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: a15375ffd6b3af7fb9119e3321495cffa00268e4
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553071"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml"></a><span data-ttu-id="ef941-103">Pobieranie kolekcji atrybutów (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="ef941-103">How to retrieve a collection of attributes (LINQ to XML)</span></span>

<span data-ttu-id="ef941-104">W tym artykule przedstawiono <xref:System.Xml.Linq.XElement.Attributes%2A> sposób użycia metody do pobrania atrybutów elementu.</span><span class="sxs-lookup"><span data-stu-id="ef941-104">This article shows the use of the <xref:System.Xml.Linq.XElement.Attributes%2A> method to retrieve the attributes of an element.</span></span>

## <a name="example-iterate-through-the-attributes-of-an-element"></a><span data-ttu-id="ef941-105">Przykład: Iterowanie przez atrybuty elementu</span><span class="sxs-lookup"><span data-stu-id="ef941-105">Example: Iterate through the attributes of an element</span></span>

<span data-ttu-id="ef941-106">Poniższy przykład pokazuje, jak wykonać iterację kolekcji atrybutów elementu.</span><span class="sxs-lookup"><span data-stu-id="ef941-106">The following example shows how to iterate through the collection of attributes of an element.</span></span>

```csharp
XElement val = new XElement("Value",
    new XAttribute("ID", "1243"),
    new XAttribute("Type", "int"),
    new XAttribute("ConvertableTo", "double"),
    "100");
IEnumerable<XAttribute> listOfAttributes =
    from att in val.Attributes()
    select att;
foreach (XAttribute a in listOfAttributes)
    Console.WriteLine(a);
```

```vb
Dim val = _
    <Value ID="1243" Type="int" ConvertableTo="double">100</Value>
Dim listOfAttributes As IEnumerable(Of XAttribute) = _
    From att In val.Attributes() _
    Select att
For Each att As XAttribute In listOfAttributes
    Console.WriteLine(att)
Next
```

<span data-ttu-id="ef941-107">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="ef941-107">This example produces the following output:</span></span>

```output
ID="1243"
Type="int"
ConvertableTo="double"
```

## <a name="see-also"></a><span data-ttu-id="ef941-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ef941-108">See also</span></span>

- [<span data-ttu-id="ef941-109">Przegląd osi LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="ef941-109">LINQ to XML axes overview</span></span>](linq-xml-axes-overview.md)
