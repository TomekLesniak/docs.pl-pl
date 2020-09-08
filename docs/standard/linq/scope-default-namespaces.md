---
title: Zakres domyślnych przestrzeni nazw — LINQ to XML
description: Domyślne przestrzenie nazw, które są reprezentowane w drzewie XML, nie są w zakresie dla zapytań. Poniżej znajdują się odpowiednie i nieprawidłowe sposoby wykonywania zapytań.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: fe826236-830f-457a-9027-7ad62c909fae
ms.openlocfilehash: 105309a70e5fbf48c4e595d4064b11fe0378f81e
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553828"
---
# <a name="scope-of-default-namespaces-linq-to-xml"></a>Zakres domyślnych przestrzeni nazw (LINQ to XML)

Domyślne przestrzenie nazw, które są reprezentowane w drzewie XML, nie są w zakresie dla zapytań. Jeśli masz kod XML, który znajduje się w domyślnym obszarze nazw, musisz połączyć przestrzeń nazw z lokalną nazwą, aby nazwa kwalifikowana była używana w zapytaniu.

Typowy błąd podczas wykonywania zapytania w drzewie XML zawierającym domyślną przestrzeń nazw polega na zapisaniu zapytania, tak jakby plik XML nie był w przestrzeni nazw. Pierwszy przykład przedstawia typowe niewłaściwe zapytanie dotyczące domyślnej przestrzeni nazw. Drugi pokazuje prawidłowe zapytanie.

## <a name="example-improper-query-of-xml-in-a-namespace"></a>Przykład: nieprawidłowe zapytanie XML w przestrzeni nazw

Ten przykład pokazuje tworzenie XML w przestrzeni nazw i niewłaściwe zapytanie zwracające pusty zestaw wyników.

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

Ten przykład generuje następujące wyniki:

```output
Result set follows:
End of result set
```

## <a name="example--proper-query-of-xml-in-a-namespace"></a>Przykład: prawidłowe zapytanie XML w przestrzeni nazw

Ten przykład pokazuje tworzenie kodu XML w przestrzeni nazw i prawidłowe zapytanie.

W języku C# poprawne podejście polega na zadeklarowaniu i zainicjowaniu <xref:System.Xml.Linq.XNamespace> obiektu oraz użyciu go podczas określania <xref:System.Xml.Linq.XName> obiektów. W tym przypadku argument <xref:System.Xml.Linq.XContainer.Elements%2A> metody jest <xref:System.Xml.Linq.XName> obiektem.

Poprawna Metoda korzystania z Visual Basic polega na zadeklarowaniu i zainicjowaniu globalnej domyślnej przestrzeni nazw. Spowoduje to umieszczenie wszystkich właściwości XML w domyślnej przestrzeni nazw.

Oto kod:

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
            Console.WriteLine(el.Value)
        Next
        Console.WriteLine("End of result set")
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```output
Result set follows:
1
2
3
End of result set
```

## <a name="see-also"></a>Zobacz też

- [Przegląd przestrzeni nazw](namespaces-overview.md)
