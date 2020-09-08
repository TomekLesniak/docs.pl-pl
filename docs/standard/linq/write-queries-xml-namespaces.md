---
title: Jak pisać zapytania dotyczące kodu XML w przestrzeniach nazw — LINQ to XML
description: Aby napisać zapytanie dotyczące kodu XML, który znajduje się w przestrzeni nazw, należy użyć obiektów XName, które mają prawidłową przestrzeń nazw. Dowiedz się, jak to zrobić w języku C# i Visual Basic oraz jak tworzyć zapytania.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
ms.openlocfilehash: 7d2c765c30409b019bf4723b9161c577e2074c04
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553029"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-linq-to-xml"></a>Jak pisać zapytania dotyczące kodu XML w przestrzeniach nazw (LINQ to XML)

Aby napisać zapytanie dotyczące kodu XML, który znajduje się w przestrzeni nazw, należy użyć <xref:System.Xml.Linq.XName> obiektów, które mają prawidłową przestrzeń nazw.

W przypadku języka C# najbardziej typowym podejściem jest zainicjowanie <xref:System.Xml.Linq.XNamespace> przy użyciu ciągu, który zawiera identyfikator URI, a następnie użycie przeciążenia operatora dodawania, aby połączyć przestrzeń nazw z nazwą lokalną.

W przypadku Visual Basic najbardziej typowym podejściem jest zdefiniowanie globalnej przestrzeni nazw, a następnie użycie literałów XML i właściwości XML, które używają globalnej przestrzeni nazw. Można zdefiniować globalną domyślną przestrzeń nazw, w której elementy case w literałach XML będą domyślnie w przestrzeni nazw. Alternatywnie można zdefiniować globalną przestrzeń nazw z prefiksem, a następnie użyć prefiksu zgodnie z wymaganiami w literałach XML i we właściwościach XML. Podobnie jak w przypadku innych form XML, atrybuty są zawsze domyślnie w żadnej przestrzeni nazw.

Pierwszy przykład w tym artykule pokazuje, jak utworzyć drzewo XML w domyślnej przestrzeni nazw. Drugi pokazuje, jak utworzyć drzewo XML w przestrzeni nazw z prefiksem.

## <a name="example-create-a-tree-in-a-default-namespace-and-retrieve-elements"></a>Przykład: Utwórz drzewo w domyślnej przestrzeni nazw i Pobierz elementy

Poniższy przykład tworzy drzewo XML, który znajduje się w domyślnej przestrzeni nazw, a następnie pobiera kolekcję elementów.

```csharp
XNamespace aw = "http://www.adventure-works.com";
XElement root = XElement.Parse(
@"<Root xmlns='http://www.adventure-works.com'>
    <Child>1</Child>
    <Child>2</Child>
    <Child>3</Child>
    <AnotherChild>4</AnotherChild>
    <AnotherChild>5</AnotherChild>
    <AnotherChild>6</AnotherChild>
</Root>");
IEnumerable<XElement> c1 =
    from el in root.Elements(aw + "Child")
    select el;
foreach (XElement el in c1)
    Console.WriteLine((int)el);
```

```vb
Imports <xmlns="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = _
            <Root>
                <Child>1</Child>
                <Child>2</Child>
                <Child>3</Child>
                <AnotherChild>4</AnotherChild>
                <AnotherChild>5</AnotherChild>
                <AnotherChild>6</AnotherChild>
            </Root>
        Dim c1 As IEnumerable(Of XElement) = _
            From el In root.<Child> _
            Select el
        For Each el As XElement In c1
            Console.WriteLine(el.Value)
        Next
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```output
1
2
3
```

## <a name="example-create-a-tree-in-a-namespace-with-a-prefix-and-retrieve-elements"></a>Przykład: Utwórz drzewo w przestrzeni nazw z prefiksem i Pobierz elementy

W języku C# zapytania są pisane w taki sam sposób, niezależnie od tego, czy piszesz zapytania w drzewie XML, który używa przestrzeni nazw z prefiksem lub w drzewie XML z domyślną przestrzenią nazw.

Poniższy przykład tworzy drzewo XML, który znajduje się w przestrzeni nazw z prefiksem, a następnie pobiera kolekcję elementów.

```csharp
XNamespace aw = "http://www.adventure-works.com";
XElement root = XElement.Parse(
@"<aw:Root xmlns:aw='http://www.adventure-works.com'>
    <aw:Child>1</aw:Child>
    <aw:Child>2</aw:Child>
    <aw:Child>3</aw:Child>
    <aw:AnotherChild>4</aw:AnotherChild>
    <aw:AnotherChild>5</aw:AnotherChild>
    <aw:AnotherChild>6</aw:AnotherChild>
</aw:Root>");
IEnumerable<XElement> c1 =
    from el in root.Elements(aw + "Child")
    select el;
foreach (XElement el in c1)
    Console.WriteLine((int)el);
```

```vb
Imports <xmlns:aw="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = _
            <aw:Root>
                <aw:Child>1</aw:Child>
                <aw:Child>2</aw:Child>
                <aw:Child>3</aw:Child>
                <aw:AnotherChild>4</aw:AnotherChild>
                <aw:AnotherChild>5</aw:AnotherChild>
                <aw:AnotherChild>6</aw:AnotherChild>
            </aw:Root>
        Dim c1 As IEnumerable(Of XElement) = _
            From el In root.<aw:Child> _
            Select el
        For Each el As XElement In c1
            Console.WriteLine(CInt(el))
        Next
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```output
1
2
3
```

## <a name="see-also"></a>Zobacz też

- [Przegląd przestrzeni nazw](namespaces-overview.md)
