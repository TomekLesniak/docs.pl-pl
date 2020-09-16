---
title: Jak odfiltrować element opcjonalny LINQ to XML
description: Można napisać wyszukiwanie elementu podrzędnego w taki sposób, aby wyszukiwanie nie powodowało wyjątku, gdy element nie istnieje.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: f99e2f93-fca5-403f-8a0c-770761d4905a
ms.openlocfilehash: 0bf4a2f2c1db420492939351795e3b66b9e0b6b7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547309"
---
# <a name="how-to-filter-on-an-optional-element-linq-to-xml"></a><span data-ttu-id="0fd96-103">Jak odfiltrować element opcjonalny (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="0fd96-103">How to filter on an optional element (LINQ to XML)</span></span>

<span data-ttu-id="0fd96-104">Czasami chcesz odfiltrować element, chociaż nie masz pewności, że istnieje w dokumencie XML.</span><span class="sxs-lookup"><span data-stu-id="0fd96-104">Sometimes you want to filter for an element even though you're not sure it exists in your XML document.</span></span> <span data-ttu-id="0fd96-105">Można napisać wyszukiwanie, tak aby, nawet jeśli określony element nie ma elementu podrzędnego, nie wyzwoli wyjątku odwołania o wartości null przez filtrowanie dla niego.</span><span class="sxs-lookup"><span data-stu-id="0fd96-105">You can write your search so that, even if the particular element doesn't have the child element, you don't trigger a null reference exception by filtering for it.</span></span>

## <a name="example-search-that-doesnt-trigger-an-exception-when-the-target-element-doesnt-exist"></a><span data-ttu-id="0fd96-106">Przykład: wyszukiwanie, które nie wyzwala wyjątku, gdy element docelowy nie istnieje</span><span class="sxs-lookup"><span data-stu-id="0fd96-106">Example: Search that doesn't trigger an exception when the target element doesn't exist</span></span>

<span data-ttu-id="0fd96-107">W poniższym przykładzie `Child5` element nie ma `Type` elementu podrzędnego, ale zapytanie jest nadal wykonywane poprawnie.</span><span class="sxs-lookup"><span data-stu-id="0fd96-107">In the following example, the `Child5` element doesn't have a `Type` child element, but the query still executes correctly.</span></span> <span data-ttu-id="0fd96-108">W przykładzie zastosowano <xref:System.Xml.Linq.Extensions.Elements%2A> metodę rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="0fd96-108">The example uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method.</span></span>

```csharp
XElement root = XElement.Parse(@"<Root>
  <Child1>
    <Text>Child One Text</Text>
    <Type Value=""Yes""/>
  </Child1>
  <Child2>
    <Text>Child Two Text</Text>
    <Type Value=""Yes""/>
  </Child2>
  <Child3>
    <Text>Child Three Text</Text>
    <Type Value=""No""/>
  </Child3>
  <Child4>
    <Text>Child Four Text</Text>
    <Type Value=""Yes""/>
  </Child4>
  <Child5>
    <Text>Child Five Text</Text>
  </Child5>
</Root>");
var cList =
    from typeElement in root.Elements().Elements("Type")
    where (string)typeElement.Attribute("Value") == "Yes"
    select (string)typeElement.Parent.Element("Text");
foreach(string str in cList)
    Console.WriteLine(str);
```

```vb
Dim root As XElement = _
    <Root>
        <Child1>
            <Text>Child One Text</Text>
            <Type Value="Yes"/>
        </Child1>
        <Child2>
            <Text>Child Two Text</Text>
            <Type Value="Yes"/>
        </Child2>
        <Child3>
            <Text>Child Three Text</Text>
            <Type Value="No"/>
        </Child3>
        <Child4>
            <Text>Child Four Text</Text>
            <Type Value="Yes"/>
        </Child4>
        <Child5>
            <Text>Child Five Text</Text>
        </Child5>
    </Root>
Dim cList As IEnumerable(Of String) = _
    From typeElement In root.Elements().<Type> _
    Where typeElement.@Value = "Yes" _
    Select typeElement.Parent.<Text>.Value
Dim str As String
For Each str In cList
    Console.WriteLine(str)
Next
```

<span data-ttu-id="0fd96-109">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="0fd96-109">This example produces the following output:</span></span>

```output
Child One Text
Child Two Text
Child Four Text
```

## <a name="example-same-search-but-for-xml-in-a-namespace"></a><span data-ttu-id="0fd96-110">Przykład: takie samo wyszukiwanie, ale w przypadku XML w przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="0fd96-110">Example: Same search but for XML in a namespace</span></span>

<span data-ttu-id="0fd96-111">Poniższy przykład to to samo zapytanie, ale w przypadku kodu XML, który znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="0fd96-111">The following example is the same query but for XML that's in a namespace.</span></span> <span data-ttu-id="0fd96-112">Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0fd96-112">For more information, see [Namespaces overview](namespaces-overview.md).</span></span>

```csharp
XElement root = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>
  <Child1>
    <Text>Child One Text</Text>
    <Type Value=""Yes""/>
  </Child1>
  <Child2>
    <Text>Child Two Text</Text>
    <Type Value=""Yes""/>
  </Child2>
  <Child3>
    <Text>Child Three Text</Text>
    <Type Value=""No""/>
  </Child3>
  <Child4>
    <Text>Child Four Text</Text>
    <Type Value=""Yes""/>
  </Child4>
  <Child5>
    <Text>Child Five Text</Text>
  </Child5>
</Root>");
XNamespace ad = "http://www.adatum.com";
var cList =
    from typeElement in root.Elements().Elements(ad + "Type")
    where (string)typeElement.Attribute("Value") == "Yes"
    select (string)typeElement.Parent.Element(ad + "Text");
foreach (string str in cList)
    Console.WriteLine(str);
```

```vb
Imports <xmlns='http://www.adatum.com'>

Module Module1
    Sub Main()
        Dim root As XElement = _
            <Root>
                <Child1>
                    <Text>Child One Text</Text>
                    <Type Value="Yes"/>
                </Child1>
                <Child2>
                    <Text>Child Two Text</Text>
                    <Type Value="Yes"/>
                </Child2>
                <Child3>
                    <Text>Child Three Text</Text>
                    <Type Value="No"/>
                </Child3>
                <Child4>
                    <Text>Child Four Text</Text>
                    <Type Value="Yes"/>
                </Child4>
                <Child5>
                    <Text>Child Five Text</Text>
                </Child5>
            </Root>
        Dim cList As IEnumerable(Of String) = _
            From typeElement In root.Elements().<Type> _
            Where typeElement.@Value = "Yes" _
            Select typeElement.Parent.<Text>.Value
        Dim str As String
        For Each str In cList
            Console.WriteLine(str)
        Next
    End Sub
End Module
```

<span data-ttu-id="0fd96-113">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="0fd96-113">This example produces the following output:</span></span>

```output
Child One Text
Child Two Text
Child Four Text
```

## <a name="see-also"></a><span data-ttu-id="0fd96-114">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0fd96-114">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0fd96-115">Standardowe operatory zapytań — Omówienie (C#)</span><span class="sxs-lookup"><span data-stu-id="0fd96-115">Standard Query Operators Overview (C#)</span></span>](../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="0fd96-116">Operacje projekcji (C#)</span><span class="sxs-lookup"><span data-stu-id="0fd96-116">Projection Operations (C#)</span></span>](../../csharp/programming-guide/concepts/linq/projection-operations.md)
- [<span data-ttu-id="0fd96-117">Zapytania podstawowe (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fd96-117">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](./find-element-specific-attribute.md)
- [<span data-ttu-id="0fd96-118">Właściwości osi elementu podrzędnego XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fd96-118">XML Child Axis Property (Visual Basic)</span></span>](../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="0fd96-119">Właściwości osi atrybutu XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fd96-119">XML Attribute Axis Property (Visual Basic)</span></span>](../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
- [<span data-ttu-id="0fd96-120">Właściwość wartości XML</span><span class="sxs-lookup"><span data-stu-id="0fd96-120">XML Value Property</span></span>](../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="0fd96-121">Standardowe operatory zapytań — Omówienie (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fd96-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="0fd96-122">Operacje projekcji (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fd96-122">Projection Operations (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
