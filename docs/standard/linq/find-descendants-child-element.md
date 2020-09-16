---
title: Jak znaleźć elementy podrzędne elementu podrzędnego — LINQ to XML
description: 'Dowiedz się, jak znaleźć elementy podrzędne elementu podrzędnego lub sekwencję elementów podrzędnych. Pokazane są dwie metody: jedna używa XPathEvaluate, drugi używa zapytania LINQ to XML.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
ms.openlocfilehash: 2ac023ddc797f27f5f00eaf86ff6357096f333c8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559316"
---
# <a name="how-to-find-descendants-of-a-child-element-linq-to-xml"></a><span data-ttu-id="a1140-104">Jak znaleźć elementy podrzędne elementu podrzędnego (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="a1140-104">How to find descendants of a child element (LINQ to XML)</span></span>

<span data-ttu-id="a1140-105">W tym artykule pokazano, jak używać <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> programu do znajdowania elementów podrzędnych sekwencji elementów podrzędnych oraz jak używać zapytania LINQ to XML, aby znaleźć te same elementy.</span><span class="sxs-lookup"><span data-stu-id="a1140-105">This article shows how to use <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> to find the descendant elements of a sequence of child elements, and how to use LINQ to XML query to find the same elements.</span></span>

## <a name="example-find-all-the-text-descendant-elements-of-all-the-paragraph-elements"></a><span data-ttu-id="a1140-106">Przykład: Znajdź wszystkie elementy `Text` podrzędne wszystkich `Paragraph` elementów</span><span class="sxs-lookup"><span data-stu-id="a1140-106">Example: Find all the `Text` descendant elements of all the `Paragraph` elements</span></span>

<span data-ttu-id="a1140-107">Ten przykład wyodrębnia tekst z reprezentacji XML prostego dokumentu przetwarzania tekstu.</span><span class="sxs-lookup"><span data-stu-id="a1140-107">This example extracts text from an XML representation of a simple word processing document.</span></span> <span data-ttu-id="a1140-108">Najpierw zaznacza wszystkie `Paragraph` elementy, ignorując `Comment` element, a następnie wybiera wszystkie `Text` elementy podrzędne każdego `Paragraph` elementu.</span><span class="sxs-lookup"><span data-stu-id="a1140-108">It first selects all `Paragraph` elements, ignoring the `Comment` element, and then it selects all the `Text` descendant elements of each `Paragraph` element.</span></span> <span data-ttu-id="a1140-109">Wykonuje to zadanie na dwa sposoby: z <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> i z LINQ to XML Query.</span><span class="sxs-lookup"><span data-stu-id="a1140-109">It does this task in two ways: with <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> and with LINQ to XML query.</span></span> <span data-ttu-id="a1140-110">Następnie porównuje wyniki i znajduje je identycznie.</span><span class="sxs-lookup"><span data-stu-id="a1140-110">It then compares the results and finds them identical.</span></span>

<span data-ttu-id="a1140-111">Wyrażenie XPath ma wartość  `./Paragraph//Text/text()` .</span><span class="sxs-lookup"><span data-stu-id="a1140-111">The XPath expression is  `./Paragraph//Text/text()`.</span></span>

```csharp
XElement root = XElement.Parse(
@"<Root>
  <Paragraph>
    <Text>This is the start of</Text>
  </Paragraph>
  <Comment>
    <Text>This comment isn't part of the paragraph text.</Text>
  </Comment>
  <Paragraph>
    <Annotation Emphasis='true'>
      <Text> a sentence.</Text>
    </Annotation>
  </Paragraph>
  <Paragraph>
    <Text>  This is the second sentence.</Text>
  </Paragraph>
</Root>");

// LINQ to XML query
string str1 =
    root
    .Elements("Paragraph")
    .Descendants("Text")
    .Select(s => s.Value)
    .Aggregate(
        new StringBuilder(),
        (s, i) => s.Append(i),
        s => s.ToString()
    );

// XPath expression
string str2 =
    ((IEnumerable)root.XPathEvaluate("./Paragraph//Text/text()"))
    .Cast<XText>()
    .Select(s => s.Value)
    .Aggregate(
        new StringBuilder(),
        (s, i) => s.Append(i),
        s => s.ToString()
    );

if (str1 == str2)
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
Console.WriteLine(str2);
```

```vb
Dim root As XElement = _
    <Root>
        <Paragraph>
            <Text>This is the start of</Text>
        </Paragraph>
        <Comment>
            <Text>This comment isn't part of the paragraph text.</Text>
        </Comment>
        <Paragraph>
            <Annotation Emphasis='true'>
                <Text> a sentence.</Text>
            </Annotation>
        </Paragraph>
        <Paragraph>
            <Text>This is the second sentence.</Text>
        </Paragraph>
    </Root>

' LINQ to XML query
Dim str1 As String = _
    root.<Paragraph>...<Text>.Select(Function(ByVal s) s.Value). _
    Aggregate( _
        New StringBuilder(), _
        Function(ByVal s, ByVal i) s.Append(i), _
        Function(ByVal s) s.ToString())

' XPath expression
Dim str2 As String = DirectCast(root.XPathEvaluate("./Paragraph//Text/text()"), IEnumerable) _
    .Cast(Of XText)().Select(Function(ByVal s) s.Value) _
    .Aggregate( _
        New StringBuilder(), _
        Function(ByVal s, ByVal i) s.Append(i), _
        Function(ByVal s) s.ToString())

If str1 = str2 Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
Console.WriteLine(str2)
```

<span data-ttu-id="a1140-112">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="a1140-112">This example produces the following output:</span></span>

```output
Results are identical
This is the start of a sentence.  This is the second sentence.
```

## <a name="see-also"></a><span data-ttu-id="a1140-113">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a1140-113">See also</span></span>

- [<span data-ttu-id="a1140-114">LINQ to XML dla użytkowników XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1140-114">LINQ to XML for XPath Users (Visual Basic)</span></span>](./comparison-xpath-linq-xml.md)
