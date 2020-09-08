---
title: Jak pobrać wartość elementu LINQ to XML
description: 'Poznaj dwa podstawowe sposoby uzyskiwania wartości elementu lub atrybutu: Rzutowanie na żądany typ lub Użyj właściwości XElement. Value i XAttribute. Value.'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: 010af5db9ec991bfe0345c93def3241150aa15e2
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553643"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml"></a>Pobieranie wartości elementu (LINQ to XML)

W tym artykule pokazano, jak uzyskać wartość elementów. Istnieją dwa podstawowe sposoby uzyskiwania wartości:

- Rzutowanie elementu <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XAttribute> na żądany typ. Operator jawnej konwersji konwertuje zawartość elementu lub atrybutu do określonego typu i przypisuje go do zmiennej.

- Użyj <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> właściwości lub <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> . Możesz również ustawić wartość przy użyciu tych właściwości.

W języku C# Rzutowanie jest ogólnie lepszym rozwiązaniem. Jeśli przerzutuje element lub atrybut do typu wartości null, kod jest łatwiejszy do zapisu podczas pobierania wartości elementu (lub atrybutu), który może nie istnieć. W ostatnim przykładzie w tym artykule pokazano, jak to zrobić. Nie można jednak ustawić zawartości elementu przez rzutowanie, jak można za pomocą <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> właściwości.

W przypadku Visual Basic lepszym rozwiązaniem jest użycie <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> właściwości.

## <a name="string-cast-example"></a>Przykład rzutowania ciągu  

Aby pobrać wartość elementu, należy rzutować <xref:System.Xml.Linq.XElement> obiekt na żądany typ. Można rzutować element na ciąg w następujący sposób:

```csharp
XElement e = new XElement("StringElement", "abcde");
Console.WriteLine(e);
Console.WriteLine("Value of e:" + (string)e);
```

```vb
Dim e As XElement = <StringElement>abcde</StringElement>
Console.WriteLine(e)
Console.WriteLine("Value of e:" & e.Value)
```

Ten przykład generuje następujące wyniki:

```output
<StringElement>abcde</StringElement>
Value of e:abcde
```

## <a name="integer-cast-example"></a>Przykład rzutowania liczby całkowitej  

Można również rzutować elementy do typów innych niż ciąg. Na przykład jeśli masz element zawierający liczbę całkowitą, możesz go rzutować na `int` , jak pokazano w poniższym kodzie:  

```csharp
XElement e = new XElement("Age", "44");
Console.WriteLine(e);
Console.WriteLine("Value of e:" + (int)e);
```

```vb
Dim e As XElement = <Age>44</Age>
Console.WriteLine(e)
Console.WriteLine("Value of e:" & CInt(e))
```

Ten przykład generuje następujące wyniki:

```output
<Age>44</Age>
Value of e:44
```

LINQ to XML zapewnia jawne Operatory rzutowania dla następujących typów danych:,,,,,,,,,,,,,,,,,,,,,, `string` `bool` `bool?` `int` `int?` `uint` `uint?` `long` `long?` `ulong` `ulong?` `float` `float?` `double` `double?` `decimal` `decimal?` `DateTime` `DateTime?` `TimeSpan` `TimeSpan?` `GUID` i `GUID?` .

LINQ to XML zapewnia te same Operatory rzutowania dla <xref:System.Xml.Linq.XAttribute> obiektów.

## <a name="value-property-example"></a>Przykład właściwości wartości

Możesz użyć właściwości, <xref:System.Xml.Linq.XElement.Value%2A> Aby pobrać zawartość elementu:

```csharp
XElement e = new XElement("StringElement", "abcde");
Console.WriteLine(e);
Console.WriteLine("Value of e:" + e.Value);
```

```vb
Dim e As XElement = <StringElement>abcde</StringElement>
Console.WriteLine(e)
Console.WriteLine("Value of e:" & e.Value)
```

Ten przykład generuje następujące wyniki:

```output
<StringElement>abcde</StringElement>
Value of e:abcde
```

## <a name="element-might-not-exist-example"></a>Element może nie istnieć przykład

Czasami próbujesz pobrać wartość elementu, mimo że nie masz pewności, czy istnieje. W tym przypadku, gdy przypiszesz element rzutowany do typu referencyjnego nullable lub typu wartości null, jeśli element nie istnieje, przypisana zmienna jest ustawiona na `null` (C#) lub `nothing` (Visual Basic). Poniższy kod pokazuje, że gdy element nie istnieje, łatwiej jest użyć rzutowania niż w celu użycia <xref:System.Xml.Linq.XElement.Value%2A> właściwości.

```csharp
XElement root = new XElement("Root",
    new XElement("Child1", "child 1 content"),
    new XElement("Child2", "2")
);

// The following assignments show why it's easier to use
// casting when the element might or might not exist.

string c1 = (string)root.Element("Child1");
Console.WriteLine("c1:{0}", c1 == null ? "element doesn't exist" : c1);

int? c2 = (int?)root.Element("Child2");
Console.WriteLine("c2:{0}", c2 == null ? "element doesn't exist" : c2.ToString());

string c3 = (string)root.Element("Child3");
Console.WriteLine("c3:{0}", c3 == null ? "element doesn't exist" : c3);

int? c4 = (int?)root.Element("Child4");
Console.WriteLine("c4:{0}", c4 == null ? "element doesn't exist" : c4.ToString());

Console.WriteLine();

// The following assignments show the required code when using
// the Value property when the element might or might not exist.
// Notice that this is more difficult than the casting approach.

XElement e1 = root.Element("Child1");
string v1;
if (e1 == null)
    v1 = null;
else
    v1 = e1.Value;
Console.WriteLine("v1:{0}", v1 == null ? "element doesn't exist" : v1);

XElement e2 = root.Element("Child2");
int? v2;
if (e2 == null)
    v2 = null;
else
    v2 = Int32.Parse(e2.Value);
Console.WriteLine("v2:{0}", v2 == null ? "element doesn't exist" : v2.ToString());

XElement e3 = root.Element("Child3");
string v3;
if (e3 == null)
    v3 = null;
else
    v3 = e3.Value;
Console.WriteLine("v3:{0}", v3 == null ? "element doesn't exist" : v3);

XElement e4 = root.Element("Child4");
int? v4;
if (e4 == null)
    v4 = null;
else
    v4 = Int32.Parse(e4.Value);
Console.WriteLine("v4:{0}", v4 == null ? "element doesn't exist" : v4.ToString());
```

```vb
Dim root As XElement = <Root>
                           <Child1>child 1 content</Child1>
                           <Child2>2</Child2>
                       </Root>

' The following assignments show why it's easier to use
' casting when the element might or might not exist.

Dim c1 As String = CStr(root.Element("Child1"))
Console.WriteLine("c1:{0}", IIf(c1 Is Nothing, "element doesn't exist", c1))

Dim c2 As Nullable(Of Integer) = CType(root.Element("Child2"), Nullable(Of Integer))
Console.WriteLine("c2:{0}", IIf(Not (c2.HasValue), "element doesn't exist", c2.ToString()))

Dim c3 As String = CStr(root.Element("Child3"))
Console.WriteLine("c3:{0}", IIf(c3 Is Nothing, "element doesn't exist", c3))

Dim c4 As Nullable(Of Integer) = CType(root.Element("Child4"), Nullable(Of Integer))
Console.WriteLine("c4:{0}", IIf(Not (c4.HasValue), "element doesn't exist", c4.ToString()))

Console.WriteLine()

' The following assignments show the required code when using
' the Value property when the attribute might or might not exist.
' Notice that this is more difficult than the casting approach.

Dim e1 As XElement = root.Element("Child1")
Dim v1 As String
If (e1 Is Nothing) Then
    v1 = Nothing
Else
    v1 = e1.Value
End If
Console.WriteLine("v1:{0}", IIf(v1 Is Nothing, "element doesn't exist", v1))

Dim e2 As XElement = root.Element("Child2")
Dim v2 As Nullable(Of Integer)
If (e2 Is Nothing) Then
    v2 = Nothing
Else
    v2 = e2.Value
End If
Console.WriteLine("v2:{0}", IIf(Not (v2.HasValue), "element doesn't exist", v2))

Dim e3 As XElement = root.Element("Child3")
Dim v3 As String
If (e3 Is Nothing) Then
    v3 = Nothing
Else
    v3 = e3.Value
End If
Console.WriteLine("v3:{0}", IIf(v3 Is Nothing, "element doesn't exist", v3))

Dim e4 As XElement = root.Element("Child4")
Dim v4 As Nullable(Of Integer)
If (e4 Is Nothing) Then
    v4 = Nothing
Else
    v4 = e4.Value
End If
Console.WriteLine("v4:{0}", IIf(Not (v4.HasValue), "element doesn't exist", v4))
```

Ten przykład generuje następujące wyniki:

```output
c1:child 1 content
c2:2
c3:element doesn't exist
c4:element doesn't exist

v1:child 1 content
v2:2
v3:element doesn't exist
v4:element doesn't exist
```

Ogólnie rzecz biorąc, można napisać łatwiejszy kod przez rzutowanie w celu pobrania zawartości elementów i atrybutów.

## <a name="see-also"></a>Zobacz też

- [Przegląd osi LINQ to XML](linq-xml-axes-overview.md)
