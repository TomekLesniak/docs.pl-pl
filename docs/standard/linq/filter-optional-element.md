---
title: Jak odfiltrować element opcjonalny LINQ to XML
description: Można napisać wyszukiwanie elementu podrzędnego w taki sposób, aby wyszukiwanie nie powodowało wyjątku, gdy element nie istnieje.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: f99e2f93-fca5-403f-8a0c-770761d4905a
ms.openlocfilehash: 0d6aa3319efb42b467782c8f09947bdae9657ab5
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552912"
---
# <a name="how-to-filter-on-an-optional-element-linq-to-xml"></a>Jak odfiltrować element opcjonalny (LINQ to XML)

Czasami chcesz odfiltrować element, chociaż nie masz pewności, że istnieje w dokumencie XML. Można napisać wyszukiwanie, tak aby, nawet jeśli określony element nie ma elementu podrzędnego, nie wyzwoli wyjątku odwołania o wartości null przez filtrowanie dla niego.

## <a name="example-search-that-doesnt-trigger-an-exception-when-the-target-element-doesnt-exist"></a>Przykład: wyszukiwanie, które nie wyzwala wyjątku, gdy element docelowy nie istnieje

W poniższym przykładzie `Child5` element nie ma `Type` elementu podrzędnego, ale zapytanie jest nadal wykonywane poprawnie. W przykładzie zastosowano <xref:System.Xml.Linq.Extensions.Elements%2A> metodę rozszerzenia.

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

Ten przykład generuje następujące wyniki:

```output
Child One Text
Child Two Text
Child Four Text
```

## <a name="example-same-search-but-for-xml-in-a-namespace"></a>Przykład: takie samo wyszukiwanie, ale w przypadku XML w przestrzeni nazw

Poniższy przykład to to samo zapytanie, ale w przypadku kodu XML, który znajduje się w przestrzeni nazw. Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

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

Ten przykład generuje następujące wyniki:

```output
Child One Text
Child Two Text
Child Four Text
```

## <a name="see-also"></a>Zobacz też

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>
- [Standardowe operatory zapytań — Omówienie (C#)](../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Operacje projekcji (C#)](../../csharp/programming-guide/concepts/linq/projection-operations.md)
- [Zapytania podstawowe (LINQ to XML) (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [Właściwości osi elementu podrzędnego XML (Visual Basic)](../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [Właściwości osi atrybutu XML (Visual Basic)](../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
- [Właściwość wartości XML](../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Standardowe operatory zapytań — Omówienie (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Operacje projekcji (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
