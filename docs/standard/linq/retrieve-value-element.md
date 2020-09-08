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
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml"></a><span data-ttu-id="f7000-103">Pobieranie wartości elementu (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="f7000-103">How to retrieve the value of an element (LINQ to XML)</span></span>

<span data-ttu-id="f7000-104">W tym artykule pokazano, jak uzyskać wartość elementów.</span><span class="sxs-lookup"><span data-stu-id="f7000-104">This article shows how to get the value of elements.</span></span> <span data-ttu-id="f7000-105">Istnieją dwa podstawowe sposoby uzyskiwania wartości:</span><span class="sxs-lookup"><span data-stu-id="f7000-105">There are two main ways to get the value:</span></span>

- <span data-ttu-id="f7000-106">Rzutowanie elementu <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XAttribute> na żądany typ.</span><span class="sxs-lookup"><span data-stu-id="f7000-106">Cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="f7000-107">Operator jawnej konwersji konwertuje zawartość elementu lub atrybutu do określonego typu i przypisuje go do zmiennej.</span><span class="sxs-lookup"><span data-stu-id="f7000-107">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span>

- <span data-ttu-id="f7000-108">Użyj <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> właściwości lub <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f7000-108">Use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> or <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="f7000-109">Możesz również ustawić wartość przy użyciu tych właściwości.</span><span class="sxs-lookup"><span data-stu-id="f7000-109">You can also set the value using these properties.</span></span>

<span data-ttu-id="f7000-110">W języku C# Rzutowanie jest ogólnie lepszym rozwiązaniem.</span><span class="sxs-lookup"><span data-stu-id="f7000-110">With C#, casting is generally the better approach.</span></span> <span data-ttu-id="f7000-111">Jeśli przerzutuje element lub atrybut do typu wartości null, kod jest łatwiejszy do zapisu podczas pobierania wartości elementu (lub atrybutu), który może nie istnieć.</span><span class="sxs-lookup"><span data-stu-id="f7000-111">If you cast the element or attribute to a nullable value type, the code is simpler to write when retrieving the value of an element (or attribute) that may not exist.</span></span> <span data-ttu-id="f7000-112">W ostatnim przykładzie w tym artykule pokazano, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="f7000-112">The last example in this article demonstrates this.</span></span> <span data-ttu-id="f7000-113">Nie można jednak ustawić zawartości elementu przez rzutowanie, jak można za pomocą <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="f7000-113">However, you can't set the contents of an element through casting, as you can through <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="f7000-114">W przypadku Visual Basic lepszym rozwiązaniem jest użycie <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="f7000-114">With Visual Basic, the better approach is to use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>

## <a name="string-cast-example"></a><span data-ttu-id="f7000-115">Przykład rzutowania ciągu</span><span class="sxs-lookup"><span data-stu-id="f7000-115">String cast example</span></span>  

<span data-ttu-id="f7000-116">Aby pobrać wartość elementu, należy rzutować <xref:System.Xml.Linq.XElement> obiekt na żądany typ.</span><span class="sxs-lookup"><span data-stu-id="f7000-116">To retrieve the value of an element, cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="f7000-117">Można rzutować element na ciąg w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="f7000-117">You can cast an element to a string, as follows:</span></span>

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

<span data-ttu-id="f7000-118">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="f7000-118">This example produces the following output:</span></span>

```output
<StringElement>abcde</StringElement>
Value of e:abcde
```

## <a name="integer-cast-example"></a><span data-ttu-id="f7000-119">Przykład rzutowania liczby całkowitej</span><span class="sxs-lookup"><span data-stu-id="f7000-119">Integer cast example</span></span>  

<span data-ttu-id="f7000-120">Można również rzutować elementy do typów innych niż ciąg.</span><span class="sxs-lookup"><span data-stu-id="f7000-120">You can also cast elements to types other than string.</span></span> <span data-ttu-id="f7000-121">Na przykład jeśli masz element zawierający liczbę całkowitą, możesz go rzutować na `int` , jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="f7000-121">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  

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

<span data-ttu-id="f7000-122">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="f7000-122">This example produces the following output:</span></span>

```output
<Age>44</Age>
Value of e:44
```

<span data-ttu-id="f7000-123">LINQ to XML zapewnia jawne Operatory rzutowania dla następujących typów danych:,,,,,,,,,,,,,,,,,,,,,, `string` `bool` `bool?` `int` `int?` `uint` `uint?` `long` `long?` `ulong` `ulong?` `float` `float?` `double` `double?` `decimal` `decimal?` `DateTime` `DateTime?` `TimeSpan` `TimeSpan?` `GUID` i `GUID?` .</span><span class="sxs-lookup"><span data-stu-id="f7000-123">LINQ to XML provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>

<span data-ttu-id="f7000-124">LINQ to XML zapewnia te same Operatory rzutowania dla <xref:System.Xml.Linq.XAttribute> obiektów.</span><span class="sxs-lookup"><span data-stu-id="f7000-124">LINQ to XML provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>

## <a name="value-property-example"></a><span data-ttu-id="f7000-125">Przykład właściwości wartości</span><span class="sxs-lookup"><span data-stu-id="f7000-125">Value property example</span></span>

<span data-ttu-id="f7000-126">Możesz użyć właściwości, <xref:System.Xml.Linq.XElement.Value%2A> Aby pobrać zawartość elementu:</span><span class="sxs-lookup"><span data-stu-id="f7000-126">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>

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

<span data-ttu-id="f7000-127">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="f7000-127">This example produces the following output:</span></span>

```output
<StringElement>abcde</StringElement>
Value of e:abcde
```

## <a name="element-might-not-exist-example"></a><span data-ttu-id="f7000-128">Element może nie istnieć przykład</span><span class="sxs-lookup"><span data-stu-id="f7000-128">Element might not exist example</span></span>

<span data-ttu-id="f7000-129">Czasami próbujesz pobrać wartość elementu, mimo że nie masz pewności, czy istnieje.</span><span class="sxs-lookup"><span data-stu-id="f7000-129">Sometimes you try to retrieve the value of an element even though you're not sure if it exists.</span></span> <span data-ttu-id="f7000-130">W tym przypadku, gdy przypiszesz element rzutowany do typu referencyjnego nullable lub typu wartości null, jeśli element nie istnieje, przypisana zmienna jest ustawiona na `null` (C#) lub `nothing` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="f7000-130">In this case, when you assign the casted element to a nullable reference type or nullable value type, if the element doesn't exist, the assigned variable is set to `null` (C#) or `nothing` (Visual Basic).</span></span> <span data-ttu-id="f7000-131">Poniższy kod pokazuje, że gdy element nie istnieje, łatwiej jest użyć rzutowania niż w celu użycia <xref:System.Xml.Linq.XElement.Value%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="f7000-131">The following code shows that when the element may not exist, it's easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>

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

<span data-ttu-id="f7000-132">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="f7000-132">This example produces the following output:</span></span>

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

<span data-ttu-id="f7000-133">Ogólnie rzecz biorąc, można napisać łatwiejszy kod przez rzutowanie w celu pobrania zawartości elementów i atrybutów.</span><span class="sxs-lookup"><span data-stu-id="f7000-133">In general, you can write simpler code by casting to retrieve the contents of elements and attributes.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7000-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f7000-134">See also</span></span>

- [<span data-ttu-id="f7000-135">Przegląd osi LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="f7000-135">LINQ to XML axes overview</span></span>](linq-xml-axes-overview.md)
