---
title: Jak znaleźć elementy z określonym atrybutem — LINQ to XML
description: 'Dowiedz się, jak znaleźć wszystkie elementy, które mają określony atrybut (bez względu na wartość). Pokazane są dwie metody: jedna używa XPathEvaluate, drugi używa zapytania LINQ to XML.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: daed00dd-923a-43be-8a90-eee406f6f574
ms.openlocfilehash: fc9f5acdda457eea1790f76695a71afe5fefa070
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552858"
---
# <a name="how-to-find-elements-with-a-specific-attribute-linq-to-xml"></a><span data-ttu-id="016d8-104">Jak znaleźć elementy z określonym atrybutem (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="016d8-104">How to find elements with a specific attribute (LINQ to XML)</span></span>

<span data-ttu-id="016d8-105">W tym artykule pokazano, jak używać <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> programu do znajdowania wszystkich elementów, które mają określony atrybut (bez względu na wartość) i jak używać zapytania LINQ to XML, aby wykonać tę samą czynność.</span><span class="sxs-lookup"><span data-stu-id="016d8-105">This article shows how to use <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> to find all elements that have a specific attribute (regardless of value), and how to use LINQ to XML query to do the same thing.</span></span>

## <a name="example-find-all-elements-that-have-the-select-attribute"></a><span data-ttu-id="016d8-106">Przykład: Znajdź wszystkie elementy, które mają `Select` atrybut</span><span class="sxs-lookup"><span data-stu-id="016d8-106">Example: Find all elements that have the `Select` attribute</span></span>

<span data-ttu-id="016d8-107">Poniższy przykład tworzy drzewo XML, a następnie znajduje elementy, które mają `Select` atrybut.</span><span class="sxs-lookup"><span data-stu-id="016d8-107">The following example creates an XML tree and then finds the elements that have the `Select` attribute.</span></span>

<span data-ttu-id="016d8-108">Wyrażenie XPath ma wartość `./*[@Select]` .</span><span class="sxs-lookup"><span data-stu-id="016d8-108">The XPath expression is `./*[@Select]`.</span></span>

```csharp
XElement doc = XElement.Parse(
@"<Root>
    <Child1>1</Child1>
    <Child2 Select='true'>2</Child2>
    <Child3>3</Child3>
    <Child4 Select='true'>4</Child4>
    <Child5>5</Child5>
</Root>");

// LINQ to XML query
IEnumerable<XElement> list1 =
    from el in doc.Elements()
    where el.Attribute("Select") != null
    select el;

// XPath expression
IEnumerable<XElement> list2 =
    ((IEnumerable)doc.XPathEvaluate("./*[@Select]")).Cast<XElement>();

if (list1.Count() == list2.Count() &&
        list1.Intersect(list2).Count() == list1.Count())
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
foreach (XElement el in list1)
    Console.WriteLine(el);
```

```vb
Dim doc As XElement = _
    <Root>
        <Child1>1</Child1>
        <Child2 Select='true'>2</Child2>
        <Child3>3</Child3>
        <Child4 Select='true'>4</Child4>
        <Child5>5</Child5>
    </Root>

' LINQ to XML query
Dim list1 As IEnumerable(Of XElement) = _
    From el In doc.Elements() _
    Where el.@Select <> Nothing _
    Select el

' XPath expression
Dim list2 As IEnumerable(Of XElement) = DirectCast(doc.XPathEvaluate _
    ("./*[@Select]"), IEnumerable).Cast(Of XElement)()

If list1.Count() = list2.Count() And _
    list1.Intersect(list2).Count() = list1.Count() Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If

For Each el As XElement In list1
    Console.WriteLine(el)
Next
```

<span data-ttu-id="016d8-109">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="016d8-109">This example produces the following output:</span></span>

```output
Results are identical
<Child2 Select="true">2</Child2>
<Child4 Select="true">4</Child4>
```

## <a name="see-also"></a><span data-ttu-id="016d8-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="016d8-110">See also</span></span>

- [<span data-ttu-id="016d8-111">LINQ to XML dla użytkowników XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="016d8-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
