---
title: Jak znaleźć bezpośrednio poprzedni element równorzędny LINQ to XML
description: 'Dowiedz się, jak znaleźć element równorzędny, który bezpośrednio poprzedza węzeł. Pokazane są dwie metody: jedna używa XPathEvaluate, drugi używa zapytania LINQ to XML.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 74c06201-0b1b-4b5e-b3ac-0092980614e6
ms.openlocfilehash: ca3f7bea150ebcfab100475ceb13b1624c91094f
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553195"
---
# <a name="how-to-find-the-immediate-preceding-sibling-linq-to-xml"></a><span data-ttu-id="b7ed8-104">Jak znaleźć bezpośrednio poprzedni element równorzędny (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="b7ed8-104">How to find the immediate preceding sibling (LINQ to XML)</span></span>

<span data-ttu-id="b7ed8-105">W tym artykule pokazano, jak użyć, <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> Aby znaleźć element równorzędny, który bezpośrednio poprzedza węzeł, i jak używać zapytania LINQ to XML, aby wykonać tę samą czynność.</span><span class="sxs-lookup"><span data-stu-id="b7ed8-105">This article shows how to use <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> to find the sibling that immediately precedes a node, and how to use LINQ to XML query to do the same thing.</span></span> <span data-ttu-id="b7ed8-106">Ze względu na różnicę w semantyce predykatów pozycyjnych dla poprzedzających osi elementów równorzędnych w XPath, w przeciwieństwie do LINQ to XML, jest to jedno z bardziej interesujących porównań.</span><span class="sxs-lookup"><span data-stu-id="b7ed8-106">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to LINQ to XML, this is one of the more interesting comparisons.</span></span>

## <a name="example-find-the-next-to-last-element"></a><span data-ttu-id="b7ed8-107">Przykład: Znajdź element obok ostatniego elementu</span><span class="sxs-lookup"><span data-stu-id="b7ed8-107">Example: Find the next to last element</span></span>

<span data-ttu-id="b7ed8-108">W tym przykładzie zapytanie LINQ to XML używa <xref:System.Linq.Enumerable.Last%2A> operatora, aby znaleźć ostatni węzeł w kolekcji zwróconej przez <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A> .</span><span class="sxs-lookup"><span data-stu-id="b7ed8-108">In this example, the LINQ to XML query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="b7ed8-109">Z kolei wyrażenie XPath używa predykatu o wartości 1, aby znaleźć bezpośrednio poprzedzający element.</span><span class="sxs-lookup"><span data-stu-id="b7ed8-109">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>

```csharp
XElement root = XElement.Parse(
    @"<Root>
    <Child1/>
    <Child2/>
    <Child3/>
    <Child4/>
</Root>");
XElement child4 = root.Element("Child4");

// LINQ to XML query
XElement el1 =
    child4
    .ElementsBeforeSelf()
    .Last();

// XPath expression
XElement el2 =
    ((IEnumerable)child4
                 .XPathEvaluate("preceding-sibling::*[1]"))
                 .Cast<XElement>()
                 .First();

if (el1 == el2)
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
Console.WriteLine(el1);
```

```vb
Dim root As XElement = _
    <Root>
        <Child1/>
        <Child2/>
        <Child3/>
        <Child4/>
    </Root>
Dim child4 As XElement = root.Element("Child4")

' LINQ to XML query
Dim el1 As XElement = child4.ElementsBeforeSelf().Last()

' XPath expression
Dim el2 As XElement = _
    DirectCast(child4.XPathEvaluate("preceding-sibling::*[1]"),  _
    IEnumerable).Cast(Of XElement)().First()

If el1 Is el2 Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
Console.WriteLine(el1)
```

<span data-ttu-id="b7ed8-110">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="b7ed8-110">This example produces the following output:</span></span>

```output
Results are identical
<Child3 />
```

## <a name="see-also"></a><span data-ttu-id="b7ed8-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b7ed8-111">See also</span></span>

- [<span data-ttu-id="b7ed8-112">LINQ to XML dla użytkowników XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7ed8-112">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
