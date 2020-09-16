---
title: Jak debugować puste zestawy wyników zapytania — LINQ to XML
description: Podczas wykonywania zapytania w drzewie XML w domyślnej przestrzeni nazw, unikaj typowego błędu zapytania, tak jakby kod XML nie był w przestrzeni nazw.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: b569f0dc-425e-45a6-acbf-770fb761c981
ms.openlocfilehash: 8fc6b1a80b183f8e2b0f80fc554a12c2657dcb55
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557143"
---
# <a name="how-to-debug-empty-query-results-sets-linq-to-xml"></a>Jak debugować puste zestawy wyników zapytania (LINQ to XML)

Jednym z najczęstszych problemów związanych z kwerendą drzewa XML jest to, że jeśli drzewo XML ma domyślną przestrzeń nazw, deweloper czasami zapisuje zapytanie tak, jakby kod XML nie był w przestrzeni nazw.

Pierwszy zestaw przykładów w tym artykule przedstawia typowy sposób ładowania kodu XML w domyślnej przestrzeni nazw, a następnie zapytanie nieprawidłowo.

Drugi zestaw przykładów pokazuje niezbędne poprawki, aby można było zbadać kod XML w przestrzeni nazw.

Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).

## <a name="example-an-improper-query-on-xml-in-a-namespace"></a>Przykład: nieprawidłowe zapytanie dotyczące kodu XML w przestrzeni nazw

Ten przykład pokazuje tworzenie XML w przestrzeni nazw i zapytanie zwracające pusty zestaw wyników.

```csharp
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
    from el in root.Elements("Child")
    select el;
Console.WriteLine("Result set follows:");
foreach (XElement el in c1)
    Console.WriteLine((int)el);
Console.WriteLine("End of result set");
```

```vb
Dim root As XElement = _
    <Root xmlns='http://www.adventure-works.com'>
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
Console.WriteLine("Result set follows:")
For Each el As XElement In c1
    Console.WriteLine(el.Value)
Next
Console.WriteLine("End of result set")
```

Przykład generuje ten wynik:

```output
Result set follows:
End of result set
```

## <a name="example-a-proper-query-on-xml-in-a-namespace"></a>Przykład: prawidłowe zapytanie dotyczące kodu XML w przestrzeni nazw

Ten przykład pokazuje tworzenie kodu XML w przestrzeni nazw oraz zakodowane prawidłowo zapytanie.

Rozwiązaniem jest zadeklarowanie i zainicjowanie <xref:System.Xml.Linq.XNamespace> obiektu oraz użycie go podczas określania <xref:System.Xml.Linq.XName> obiektów. W tym przypadku argument <xref:System.Xml.Linq.XContainer.Elements%2A> metody jest <xref:System.Xml.Linq.XName> obiektem.

```csharp
XElement root = XElement.Parse(
@"<Root xmlns='http://www.adventure-works.com'>
    <Child>1</Child>
    <Child>2</Child>
    <Child>3</Child>
    <AnotherChild>4</AnotherChild>
    <AnotherChild>5</AnotherChild>
    <AnotherChild>6</AnotherChild>
</Root>");
XNamespace aw = "http://www.adventure-works.com";
IEnumerable<XElement> c1 =
    from el in root.Elements(aw + "Child")
    select el;
Console.WriteLine("Result set follows:");
foreach (XElement el in c1)
    Console.WriteLine((int)el);
Console.WriteLine("End of result set");
```

```vb
Imports <xmlns="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = _
            <Root xmlns='http://www.adventure-works.com'>
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
        Console.WriteLine("Result set follows:")
        For Each el As XElement In c1
            Console.WriteLine(CInt(el))
        Next
        Console.WriteLine("End of result set")
    End Sub
End Module
```

Przykład generuje ten wynik:

```output
Result set follows:
1
2
3
End of result set
```

## <a name="see-also"></a>Zobacz także

- [Zapytania podstawowe (LINQ to XML) (Visual Basic)](./find-element-specific-attribute.md)
