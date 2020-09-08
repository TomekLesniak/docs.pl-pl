---
title: Przedrozproszenie obiektów XName — LINQ to XML
description: Dowiedz się, jak wstępnie wyodrębnić, aby zwiększyć wydajność podczas tworzenia dużej liczby elementów o tej samej nazwie.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: e84fbbe7-f072-4771-bfbb-059d18e1ad15
ms.openlocfilehash: 97da1e09e246491d8427c7a69953e006c80475a4
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553086"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml"></a>Rozproszenie obiektów XName (LINQ to XML)

Jednym ze sposobów poprawy wydajności LINQ to XML jest wyodrębnić <xref:System.Xml.Linq.XName> obiektów. Rozproszenie oznacza przypisanie ciągu do <xref:System.Xml.Linq.XName> obiektu przed utworzeniem drzewa XML przy użyciu konstruktorów <xref:System.Xml.Linq.XElement>  <xref:System.Xml.Linq.XAttribute> klas i. Następnie zamiast przekazywania ciągu do konstruktora, który mógłby użyć niejawnej konwersji z ciągu na <xref:System.Xml.Linq.XName> , należy przekazać zainicjowany <xref:System.Xml.Linq.XName> obiekt.

Zwiększa to wydajność podczas tworzenia dużych drzew XML, w których nazwy są powtarzane. W tym celu należy zadeklarować i zainicjować <xref:System.Xml.Linq.XName> obiekty przed rozpoczęciem tworzenia drzewa XML, a następnie użyć <xref:System.Xml.Linq.XName> obiektów zamiast określania ciągów nazw elementów i atrybutów. Ta technika może przynieść znaczący wzrost wydajności w przypadku tworzenia dużej liczby elementów lub atrybutów o tej samej nazwie.

Należy przetestować rozproszenie z Twoim scenariuszem, aby zdecydować, czy należy z niego korzystać.

## <a name="example-create-elements-in-various-ways-with-and-without-pre-atomization"></a>Przykład: Tworzenie elementów na różne sposoby, z i bez przedrozproszenie

Poniższy przykład demonstruje rozproszenie.

```csharp
XName Root = "Root";
XName Data = "Data";
XName ID = "ID";

XElement root = new XElement(Root,
    new XElement(Data,
        new XAttribute(ID, "1"),
        "4,100,000"),
    new XElement(Data,
        new XAttribute(ID, "2"),
        "3,700,000"),
    new XElement(Data,
        new XAttribute(ID, "3"),
        "1,150,000")
);

Console.WriteLine(root);
```

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

Ten przykład generuje następujące wyniki:

```xml
<Root>
  <Data ID="1">4,100,000</Data>
  <Data ID="2">3,700,000</Data>
  <Data ID="3">1,150,000</Data>
</Root>
```

Poniższy przykład pokazuje tę samą technikę dla dokumentu XML w przestrzeni nazw:

```csharp
XNamespace aw = "http://www.adventure-works.com";
XName Root = aw + "Root";
XName Data = aw + "Data";
XName ID = "ID";

XElement root = new XElement(Root,
    new XAttribute(XNamespace.Xmlns + "aw", aw),
    new XElement(Data,
        new XAttribute(ID, "1"),
        "4,100,000"),
    new XElement(Data,
        new XAttribute(ID, "2"),
        "3,700,000"),
    new XElement(Data,
        new XAttribute(ID, "3"),
        "1,150,000")
);

Console.WriteLine(root);
```

```vb
Dim aw As XNamespace = "http://www.adventure-works.com"
Dim root1 As XName = aw + "Root"
Dim data As XName = aw + "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XAttribute(XNamespace.Xmlns + "aw", aw),
                          New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

Ten przykład generuje następujące wyniki:

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Data ID="1">4,100,000</aw:Data>
  <aw:Data ID="2">3,700,000</aw:Data>
  <aw:Data ID="3">1,150,000</aw:Data>
</aw:Root>
```

Poniższy przykład jest bardziej podobny do tego, co prawdopodobnie napotkasz w świecie rzeczywistym. W tym przykładzie zawartość elementu jest dostarczana przez zapytanie:

```csharp
XName Root = "Root";
XName Data = "Data";
XName ID = "ID";

DateTime t1 = DateTime.Now;
XElement root = new XElement(Root,
    from i in System.Linq.Enumerable.Range(1, 100000)
    select new XElement(Data,
        new XAttribute(ID, i),
        i * 5)
);
DateTime t2 = DateTime.Now;

Console.WriteLine("Time to construct:{0}", t2 - t1);
```

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"

Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root2 As New XElement(root1, From i In Enumerable.Range(1, 100000)
                                 Select New XElement(data, New XAttribute(ID, i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```

Poprzedni przykład wykonuje lepsze niż Poniższy przykład, w którym nazwy nie są wstępnie atomne:

```csharp
DateTime t1 = DateTime.Now;
XElement root = new XElement("Root",
    from i in System.Linq.Enumerable.Range(1, 100000)
    select new XElement("Data",
        new XAttribute("ID", i),
        i * 5)
);
DateTime t2 = DateTime.Now;

Console.WriteLine("Time to construct:{0}", t2 - t1);
```

```vb
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root As New XElement("Root", From i In Enumerable.Range(1, 100000)
                                 Select New XElement("Data", New XAttribute("ID", i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```

## <a name="see-also"></a>Zobacz też

- [Atomowe obiekty XName i XNamespace](atomized-xname-xnamespace-objects.md)
