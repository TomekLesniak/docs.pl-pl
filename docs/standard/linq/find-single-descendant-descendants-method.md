---
title: Jak znaleźć pojedynczy element podrzędny przy użyciu metody Descendants-LINQ to XML
description: Użyj metody osi XContainer. Descendants, aby znaleźć pojedynczy element podrzędny o unikatowej nazwie.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 6f735be9-0293-4680-8007-ca9d96bfebed
ms.openlocfilehash: 9065309822bfb7c46da556fcf9b3a3b48df16302
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553155"
---
# <a name="how-to-find-a-single-descendant-using-the-descendants-method-linq-to-xml"></a>Jak znaleźć pojedynczy element podrzędny przy użyciu metody Descendants (LINQ to XML)

Możesz użyć <xref:System.Xml.Linq.XContainer.Descendants%2A> metody osi, aby znaleźć pojedynczy element potomny o unikatowej nazwie. Ta technika jest szczególnie przydatna, gdy chcesz znaleźć konkretny element podrzędny o określonej nazwie i może być szybszy i łatwiejszy w użyciu niż nawigowanie po drzewie XML.

## <a name="example-use-xcontainerdescendants-to-find-a-single-uniquely-named-descendant-element"></a>Przykład: Użyj XContainer. Descendants, aby znaleźć pojedynczy element potomny o unikatowej nazwie

W tym przykładzie użyto <xref:System.Linq.Enumerable.First%2A> standardowego operatora zapytania.

```csharp
XElement root = XElement.Parse(@"<Root>
  <Child1>
    <GrandChild1>GC1 Value</GrandChild1>
  </Child1>
  <Child2>
    <GrandChild2>GC2 Value</GrandChild2>
  </Child2>
  <Child3>
    <GrandChild3>GC3 Value</GrandChild3>
  </Child3>
  <Child4>
    <GrandChild4>GC4 Value</GrandChild4>
  </Child4>
</Root>");
string grandChild3 = (string)
    (from el in root.Descendants("GrandChild3")
    select el).First();
Console.WriteLine(grandChild3);
```

```vb
Dim root As XElement = _
    <Root>
        <Child1>
            <GrandChild1>GC1 Value</GrandChild1>
        </Child1>
        <Child2>
            <GrandChild2>GC2 Value</GrandChild2>
        </Child2>
        <Child3>
            <GrandChild3>GC3 Value</GrandChild3>
        </Child3>
        <Child4>
            <GrandChild4>GC4 Value</GrandChild4>
        </Child4>
    </Root>
Dim grandChild3 As String = _
    (From el In root...<GrandChild3> _
    Select el).First()
Console.WriteLine(grandChild3)
```

Ten przykład generuje następujące wyniki:

```output
GC3 Value
```

## <a name="example-find-when-the-xml-is-in-a-namespace"></a>Przykład: Znajdź, kiedy plik XML znajduje się w przestrzeni nazw

Poniższy przykład jest taki sam jak poprzedni, ale dla XML, który znajduje się w przestrzeni nazw. Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

```csharp
XElement root = XElement.Parse(@"<aw:Root xmlns:aw='http://www.adventure-works.com'>
  <aw:Child1>
    <aw:GrandChild1>GC1 Value</aw:GrandChild1>
  </aw:Child1>
  <aw:Child2>
    <aw:GrandChild2>GC2 Value</aw:GrandChild2>
  </aw:Child2>
  <aw:Child3>
    <aw:GrandChild3>GC3 Value</aw:GrandChild3>
  </aw:Child3>
  <aw:Child4>
    <aw:GrandChild4>GC4 Value</aw:GrandChild4>
  </aw:Child4>
</aw:Root>");
XNamespace aw = "http://www.adventure-works.com";
string grandChild3 = (string)
    (from el in root.Descendants(aw + "GrandChild3")
     select el).First();
Console.WriteLine(grandChild3);
```

```vb
Imports <xmlns:aw='http://www.adventure-works.com'>

Module Module1
    Sub Main()
        Dim root As XElement = _
            <aw:Root>
                <aw:Child1>
                    <aw:GrandChild1>GC1 Value</aw:GrandChild1>
                </aw:Child1>
                <aw:Child2>
                    <aw:GrandChild2>GC2 Value</aw:GrandChild2>
                </aw:Child2>
                <aw:Child3>
                    <aw:GrandChild3>GC3 Value</aw:GrandChild3>
                </aw:Child3>
                <aw:Child4>
                    <aw:GrandChild4>GC4 Value</aw:GrandChild4>
                </aw:Child4>
            </aw:Root>
        Dim grandChild3 As String = _
            (From el In root...<aw:GrandChild3> _
            Select el).First()
        Console.WriteLine(grandChild3)
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```output
GC3 Value
```
