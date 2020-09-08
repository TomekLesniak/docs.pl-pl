---
title: Jak znaleźć elementy podrzędne elementu podrzędnego — LINQ to XML
description: 'Dowiedz się, jak znaleźć elementy podrzędne elementu podrzędnego lub sekwencję elementów podrzędnych. Pokazane są dwie metody: jedna używa XPathEvaluate, drugi używa zapytania LINQ to XML.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
ms.openlocfilehash: 675fb7da42f874e21374a6fbc4b61ae90a78caf2
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552876"
---
# <a name="how-to-find-descendants-of-a-child-element-linq-to-xml"></a>Jak znaleźć elementy podrzędne elementu podrzędnego (LINQ to XML)

W tym artykule pokazano, jak używać <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> programu do znajdowania elementów podrzędnych sekwencji elementów podrzędnych oraz jak używać zapytania LINQ to XML, aby znaleźć te same elementy.

## <a name="example-find-all-the-text-descendant-elements-of-all-the-paragraph-elements"></a>Przykład: Znajdź wszystkie elementy `Text` podrzędne wszystkich `Paragraph` elementów

Ten przykład wyodrębnia tekst z reprezentacji XML prostego dokumentu przetwarzania tekstu. Najpierw zaznacza wszystkie `Paragraph` elementy, ignorując `Comment` element, a następnie wybiera wszystkie `Text` elementy podrzędne każdego `Paragraph` elementu. Wykonuje to zadanie na dwa sposoby: z <xref:System.Xml.XPath.Extensions.XPathEvaluate%2A> i z LINQ to XML Query. Następnie porównuje wyniki i znajduje je identycznie.

Wyrażenie XPath ma wartość  `./Paragraph//Text/text()` .

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

Ten przykład generuje następujące wyniki:

```output
Results are identical
This is the start of a sentence.  This is the second sentence.
```

## <a name="see-also"></a>Zobacz też

- [LINQ to XML dla użytkowników XPath (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
