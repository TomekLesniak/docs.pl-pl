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
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml"></a>Pobieranie wartości atrybutu (LINQ to XML)

W tym artykule pokazano, jak uzyskać wartość atrybutów. Istnieją dwa podstawowe sposoby: można rzutować <xref:System.Xml.Linq.XAttribute> na żądany typ; operator jawnej konwersji następnie konwertuje zawartość elementu lub atrybutu do określonego typu. Alternatywnie można użyć <xref:System.Xml.Linq.XAttribute.Value%2A> właściwości. Jednak Rzutowanie jest ogólnie lepszym rozwiązaniem. Jeśli rzutowanie atrybutu na typ wartości null, kod jest łatwiejszy do zapisu podczas pobierania wartości atrybutu, który może lub nie istnieje. Aby zapoznać się z przykładami tej techniki, zobacz [jak pobrać wartość elementu](retrieve-value-element.md).

## <a name="example-use-a-cast-to-retrieve-the-value-of-an-attribute"></a>Przykład: Użyj rzutowania, aby pobrać wartość atrybutu

Aby pobrać wartość atrybutu w języku C#, należy rzutować <xref:System.Xml.Linq.XAttribute> obiekt na żądany typ. W Visual Basic można użyć właściwości Integrated Attribute, aby pobrać wartość.

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

Ten przykład generuje następujące wyniki:

```output
<Root Attr="abcde" />
abcde
```

## <a name="example-use-a-cast-to-retrieve-from-xml-thats-in-a-namespace"></a>Przykład: Użyj rzutowania do pobrania z XML, który znajduje się w przestrzeni nazw

Poniższy przykład pokazuje, jak pobrać wartość atrybutu, jeśli atrybut znajduje się w przestrzeni nazw. Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

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

Ten przykład generuje następujące wyniki:

```output
abcde
```

## <a name="see-also"></a>Zobacz też

- [Przegląd osi LINQ to XML](linq-xml-axes-overview.md)
