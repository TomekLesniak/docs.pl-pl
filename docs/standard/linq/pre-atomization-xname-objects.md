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
# <a name="pre-atomization-of-xname-objects-linq-to-xml"></a><span data-ttu-id="5bd0a-103">Rozproszenie obiektów XName (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="5bd0a-103">Pre-Atomization of XName objects (LINQ to XML)</span></span>

<span data-ttu-id="5bd0a-104">Jednym ze sposobów poprawy wydajności LINQ to XML jest wyodrębnić <xref:System.Xml.Linq.XName> obiektów.</span><span class="sxs-lookup"><span data-stu-id="5bd0a-104">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="5bd0a-105">Rozproszenie oznacza przypisanie ciągu do <xref:System.Xml.Linq.XName> obiektu przed utworzeniem drzewa XML przy użyciu konstruktorów <xref:System.Xml.Linq.XElement>  <xref:System.Xml.Linq.XAttribute> klas i.</span><span class="sxs-lookup"><span data-stu-id="5bd0a-105">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and  <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="5bd0a-106">Następnie zamiast przekazywania ciągu do konstruktora, który mógłby użyć niejawnej konwersji z ciągu na <xref:System.Xml.Linq.XName> , należy przekazać zainicjowany <xref:System.Xml.Linq.XName> obiekt.</span><span class="sxs-lookup"><span data-stu-id="5bd0a-106">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>

<span data-ttu-id="5bd0a-107">Zwiększa to wydajność podczas tworzenia dużych drzew XML, w których nazwy są powtarzane.</span><span class="sxs-lookup"><span data-stu-id="5bd0a-107">This improves performance when you create a large XML tree in which names are repeated.</span></span> <span data-ttu-id="5bd0a-108">W tym celu należy zadeklarować i zainicjować <xref:System.Xml.Linq.XName> obiekty przed rozpoczęciem tworzenia drzewa XML, a następnie użyć <xref:System.Xml.Linq.XName> obiektów zamiast określania ciągów nazw elementów i atrybutów.</span><span class="sxs-lookup"><span data-stu-id="5bd0a-108">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="5bd0a-109">Ta technika może przynieść znaczący wzrost wydajności w przypadku tworzenia dużej liczby elementów lub atrybutów o tej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="5bd0a-109">This technique can yield significant performance gains if you're creating a large number of elements or attributes with the same name.</span></span>

<span data-ttu-id="5bd0a-110">Należy przetestować rozproszenie z Twoim scenariuszem, aby zdecydować, czy należy z niego korzystać.</span><span class="sxs-lookup"><span data-stu-id="5bd0a-110">You should test pre-atomization with your scenario to decide if you should use it.</span></span>

## <a name="example-create-elements-in-various-ways-with-and-without-pre-atomization"></a><span data-ttu-id="5bd0a-111">Przykład: Tworzenie elementów na różne sposoby, z i bez przedrozproszenie</span><span class="sxs-lookup"><span data-stu-id="5bd0a-111">Example: Create elements in various ways, with and without pre-atomization</span></span>

<span data-ttu-id="5bd0a-112">Poniższy przykład demonstruje rozproszenie.</span><span class="sxs-lookup"><span data-stu-id="5bd0a-112">The following example demonstrates pre-atomization.</span></span>

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

<span data-ttu-id="5bd0a-113">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="5bd0a-113">This example produces the following output:</span></span>

```xml
<Root>
  <Data ID="1">4,100,000</Data>
  <Data ID="2">3,700,000</Data>
  <Data ID="3">1,150,000</Data>
</Root>
```

<span data-ttu-id="5bd0a-114">Poniższy przykład pokazuje tę samą technikę dla dokumentu XML w przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="5bd0a-114">The following example shows the same technique for an XML document in a namespace:</span></span>

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

<span data-ttu-id="5bd0a-115">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="5bd0a-115">This example produces the following output:</span></span>

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Data ID="1">4,100,000</aw:Data>
  <aw:Data ID="2">3,700,000</aw:Data>
  <aw:Data ID="3">1,150,000</aw:Data>
</aw:Root>
```

<span data-ttu-id="5bd0a-116">Poniższy przykład jest bardziej podobny do tego, co prawdopodobnie napotkasz w świecie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="5bd0a-116">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="5bd0a-117">W tym przykładzie zawartość elementu jest dostarczana przez zapytanie:</span><span class="sxs-lookup"><span data-stu-id="5bd0a-117">In this example, the content of the element is supplied by a query:</span></span>

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

<span data-ttu-id="5bd0a-118">Poprzedni przykład wykonuje lepsze niż Poniższy przykład, w którym nazwy nie są wstępnie atomne:</span><span class="sxs-lookup"><span data-stu-id="5bd0a-118">The previous example performs better than the following example, in which names aren't pre-atomized:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5bd0a-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5bd0a-119">See also</span></span>

- [<span data-ttu-id="5bd0a-120">Atomowe obiekty XName i XNamespace</span><span class="sxs-lookup"><span data-stu-id="5bd0a-120">Atomized XName and XNamespace objects</span></span>](atomized-xname-xnamespace-objects.md)
