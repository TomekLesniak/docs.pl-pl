---
title: Jak pobrać wartość atrybutu-LINQ to XML
description: Pobierz wartość atrybutu. Można rzutować XAttribute na żądany typ lub użyć właściwości XAttribute. Value.
ms.date: 07/20/2015
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
ms.openlocfilehash: 7af3616c9808cad5dfb52f53c74b21a59da5c954
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553651"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml"></a><span data-ttu-id="17e74-104">Pobieranie wartości atrybutu (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="17e74-104">How to retrieve the value of an attribute (LINQ to XML)</span></span>

<span data-ttu-id="17e74-105">W tym artykule pokazano, jak uzyskać wartość atrybutów.</span><span class="sxs-lookup"><span data-stu-id="17e74-105">This article shows how to obtain the value of attributes.</span></span> <span data-ttu-id="17e74-106">Istnieją dwa podstawowe sposoby: można rzutować <xref:System.Xml.Linq.XAttribute> na żądany typ; operator jawnej konwersji następnie konwertuje zawartość elementu lub atrybutu do określonego typu.</span><span class="sxs-lookup"><span data-stu-id="17e74-106">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="17e74-107">Alternatywnie można użyć <xref:System.Xml.Linq.XAttribute.Value%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="17e74-107">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="17e74-108">Jednak Rzutowanie jest ogólnie lepszym rozwiązaniem.</span><span class="sxs-lookup"><span data-stu-id="17e74-108">However, casting is generally the better approach.</span></span> <span data-ttu-id="17e74-109">Jeśli rzutowanie atrybutu na typ wartości null, kod jest łatwiejszy do zapisu podczas pobierania wartości atrybutu, który może lub nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="17e74-109">If you cast the attribute to a nullable value type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="17e74-110">Aby zapoznać się z przykładami tej techniki, zobacz [jak pobrać wartość elementu](retrieve-value-element.md).</span><span class="sxs-lookup"><span data-stu-id="17e74-110">For examples of this technique, see [How to retrieve the value of an element](retrieve-value-element.md).</span></span>

## <a name="example-use-a-cast-to-retrieve-the-value-of-an-attribute"></a><span data-ttu-id="17e74-111">Przykład: Użyj rzutowania, aby pobrać wartość atrybutu</span><span class="sxs-lookup"><span data-stu-id="17e74-111">Example: Use a cast to retrieve the value of an attribute</span></span>

<span data-ttu-id="17e74-112">Aby pobrać wartość atrybutu w języku C#, należy rzutować <xref:System.Xml.Linq.XAttribute> obiekt na żądany typ.</span><span class="sxs-lookup"><span data-stu-id="17e74-112">To retrieve the value of an attribute in C#, you cast the <xref:System.Xml.Linq.XAttribute> object to your desired type.</span></span> <span data-ttu-id="17e74-113">W Visual Basic można użyć właściwości Integrated Attribute, aby pobrać wartość.</span><span class="sxs-lookup"><span data-stu-id="17e74-113">In Visual Basic, you can use the integrated attribute property to retrieve the value.</span></span>

```csharp
XElement root = new XElement("Root",
                    new XAttribute("Attr", "abcde")
                );
Console.WriteLine(root);
string str = (string)root.Attribute("Attr");
Console.WriteLine(str);
```

```vb
Dim root As XElement = <Root Attr="abcde"/>
Console.WriteLine(root)
Dim str As String = root.@Attr
Console.WriteLine(str)
```

<span data-ttu-id="17e74-114">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="17e74-114">This example produces the following output:</span></span>

```output
<Root Attr="abcde" />
abcde
```

## <a name="example-use-a-cast-to-retrieve-from-xml-thats-in-a-namespace"></a><span data-ttu-id="17e74-115">Przykład: Użyj rzutowania do pobrania z XML, który znajduje się w przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="17e74-115">Example: Use a cast to retrieve from XML that's in a namespace</span></span>

<span data-ttu-id="17e74-116">Poniższy przykład pokazuje, jak pobrać wartość atrybutu, jeśli atrybut znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="17e74-116">The following example shows how to retrieve the value of an attribute if the attribute is in a namespace.</span></span> <span data-ttu-id="17e74-117">Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).</span><span class="sxs-lookup"><span data-stu-id="17e74-117">For more information, see [Namespaces overview](namespaces-overview.md).</span></span>

```csharp
XNamespace aw = "http://www.adventure-works.com";
XElement root = new XElement(aw + "Root",
                    new XAttribute(aw + "Attr", "abcde")
                );
string str = (string)root.Attribute(aw + "Attr");
Console.WriteLine(str);
```

```vb
Imports <xmlns:aw="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = <aw:Root aw:Attr="abcde"/>
        Dim str As String = root.@aw:Attr
        Console.WriteLine(str)
    End Sub
End Module
```

<span data-ttu-id="17e74-118">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="17e74-118">This example produces the following output:</span></span>

```output
abcde
```

## <a name="see-also"></a><span data-ttu-id="17e74-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="17e74-119">See also</span></span>

- [<span data-ttu-id="17e74-120">Przegląd osi LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="17e74-120">LINQ to XML axes overview</span></span>](linq-xml-axes-overview.md)
