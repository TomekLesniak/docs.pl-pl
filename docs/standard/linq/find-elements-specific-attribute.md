---
title: Jak znaleźć elementy z określonym atrybutem — LINQ to XML
description: 'Dowiedz się, jak znaleźć wszystkie elementy, które mają określony atrybut (bez względu na wartość). Pokazane są dwie metody: jedna używa XPathEvaluate, drugi używa zapytania LINQ to XML.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: daed00dd-923a-43be-8a90-eee406f6f574
ms.openlocfilehash: 2a747e7609e2b130249a7635d8448577d035f939
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545650"
---
# <a name="how-to-find-elements-with-a-specific-attribute-linq-to-xml"></a>Jak znaleźć elementy z określonym atrybutem (LINQ to XML)

W tym artykule pokazano, jak używać <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> programu do znajdowania wszystkich elementów, które mają określony atrybut (bez względu na wartość) i jak używać zapytania LINQ to XML, aby wykonać tę samą czynność.

## <a name="example-find-all-elements-that-have-the-select-attribute"></a>Przykład: Znajdź wszystkie elementy, które mają `Select` atrybut

Poniższy przykład tworzy drzewo XML, a następnie znajduje elementy, które mają `Select` atrybut.

Wyrażenie XPath ma wartość `./*[@Select]` .

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

Ten przykład generuje następujące wyniki:

```output
Results are identical
<Child2 Select="true">2</Child2>
<Child4 Select="true">4</Child4>
```

## <a name="see-also"></a>Zobacz także

- [LINQ to XML dla użytkowników XPath (Visual Basic)](./comparison-xpath-linq-xml.md)
