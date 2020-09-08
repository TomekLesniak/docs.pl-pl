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
# <a name="how-to-find-the-immediate-preceding-sibling-linq-to-xml"></a>Jak znaleźć bezpośrednio poprzedni element równorzędny (LINQ to XML)

W tym artykule pokazano, jak użyć, <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> Aby znaleźć element równorzędny, który bezpośrednio poprzedza węzeł, i jak używać zapytania LINQ to XML, aby wykonać tę samą czynność. Ze względu na różnicę w semantyce predykatów pozycyjnych dla poprzedzających osi elementów równorzędnych w XPath, w przeciwieństwie do LINQ to XML, jest to jedno z bardziej interesujących porównań.

## <a name="example-find-the-next-to-last-element"></a>Przykład: Znajdź element obok ostatniego elementu

W tym przykładzie zapytanie LINQ to XML używa <xref:System.Linq.Enumerable.Last%2A> operatora, aby znaleźć ostatni węzeł w kolekcji zwróconej przez <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A> . Z kolei wyrażenie XPath używa predykatu o wartości 1, aby znaleźć bezpośrednio poprzedzający element.

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

Ten przykład generuje następujące wyniki:

```output
Results are identical
<Child3 />
```

## <a name="see-also"></a>Zobacz też

- [LINQ to XML dla użytkowników XPath (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
