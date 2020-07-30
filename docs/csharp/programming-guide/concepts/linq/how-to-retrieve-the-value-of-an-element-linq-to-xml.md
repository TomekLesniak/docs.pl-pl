---
title: Jak pobrać wartość elementu (LINQ to XML) (C#)
description: Dowiedz się, jak uzyskać wartość elementów. Zobacz przykłady użycia rzutowania ciągów, rzutowania liczb całkowitych i właściwości Value.
ms.date: 07/20/2015
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: eb750927d74c3068d7ab06caba9835110bd77a09
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301544"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a><span data-ttu-id="2f6a4-104">Jak pobrać wartość elementu (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2f6a4-104">How to retrieve the value of an element (LINQ to XML) (C#)</span></span>

<span data-ttu-id="2f6a4-105">W tym artykule pokazano, jak uzyskać wartość elementów.</span><span class="sxs-lookup"><span data-stu-id="2f6a4-105">This article shows how to get the value of elements.</span></span> <span data-ttu-id="2f6a4-106">Istnieją dwa podstawowe sposoby uzyskiwania wartości:</span><span class="sxs-lookup"><span data-stu-id="2f6a4-106">There are two main ways to get the value:</span></span>

- <span data-ttu-id="2f6a4-107">Rzutowanie elementu <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XAttribute> na żądany typ.</span><span class="sxs-lookup"><span data-stu-id="2f6a4-107">Cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="2f6a4-108">Operator jawnej konwersji konwertuje zawartość elementu lub atrybutu do określonego typu i przypisuje go do zmiennej.</span><span class="sxs-lookup"><span data-stu-id="2f6a4-108">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span>

- <span data-ttu-id="2f6a4-109">Użyj <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> właściwości lub <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2f6a4-109">Use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> or <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="2f6a4-110">Możesz również ustawić wartość przy użyciu tych właściwości.</span><span class="sxs-lookup"><span data-stu-id="2f6a4-110">You can also set the value using these properties.</span></span>

<span data-ttu-id="2f6a4-111">W języku C# Rzutowanie jest ogólnie lepszym rozwiązaniem.</span><span class="sxs-lookup"><span data-stu-id="2f6a4-111">With C#, casting is generally the better approach.</span></span> <span data-ttu-id="2f6a4-112">Jeśli przerzutuje element lub atrybut do typu wartości null, kod jest łatwiejszy do zapisu podczas pobierania wartości elementu (lub atrybutu), który może lub nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="2f6a4-112">If you cast the element or attribute to a nullable value type, the code is simpler to write when retrieving the value of an element (or attribute) that might or might not exist.</span></span> <span data-ttu-id="2f6a4-113">[Ostatni przykład](#element-might-not-exist-example) w tym artykule pokazuje, że Rzutowanie jest prostsze w przypadku, gdy element może nie istnieć.</span><span class="sxs-lookup"><span data-stu-id="2f6a4-113">The [last example](#element-might-not-exist-example) in this article demonstrates that casting is simpler in the case where the element might not exist.</span></span> <span data-ttu-id="2f6a4-114">Nie można jednak ustawić zawartości elementu przez rzutowanie, jak można za pomocą <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="2f6a4-114">However, you cannot set the contents of an element through casting, as you can through <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="string-cast-example"></a><span data-ttu-id="2f6a4-115">Przykład rzutowania ciągu</span><span class="sxs-lookup"><span data-stu-id="2f6a4-115">String cast example</span></span>  
 <span data-ttu-id="2f6a4-116">Aby pobrać wartość elementu, należy rzutować <xref:System.Xml.Linq.XElement> obiekt na żądany typ.</span><span class="sxs-lookup"><span data-stu-id="2f6a4-116">To retrieve the value of an element, cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="2f6a4-117">Można rzutować element na ciąg w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="2f6a4-117">You can cast an element to a string, as follows:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 <span data-ttu-id="2f6a4-118">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="2f6a4-118">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="integer-cast-example"></a><span data-ttu-id="2f6a4-119">Przykład rzutowania liczby całkowitej</span><span class="sxs-lookup"><span data-stu-id="2f6a4-119">Integer cast example</span></span>  
 <span data-ttu-id="2f6a4-120">Można również rzutować elementy do typów innych niż ciąg.</span><span class="sxs-lookup"><span data-stu-id="2f6a4-120">You can also cast elements to types other than string.</span></span> <span data-ttu-id="2f6a4-121">Na przykład jeśli masz element zawierający liczbę całkowitą, możesz go rzutować na `int` , jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="2f6a4-121">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 <span data-ttu-id="2f6a4-122">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="2f6a4-122">This example produces the following output:</span></span>  
  
```output  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="2f6a4-123">zapewnia jawne Operatory rzutowania dla następujących typów danych:,,,,,,,,,, `string` `bool` `bool?` `int` `int?` `uint` `uint?` `long` `long?` `ulong` `ulong?` , `float` , `float?` , `double` ,,,,,, `double?` `decimal` `decimal?` `DateTime` `DateTime?` `TimeSpan` , `TimeSpan?` ,, `GUID` i `GUID?` .</span><span class="sxs-lookup"><span data-stu-id="2f6a4-123">provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="2f6a4-124">zapewnia te same Operatory rzutowania dla <xref:System.Xml.Linq.XAttribute> obiektów.</span><span class="sxs-lookup"><span data-stu-id="2f6a4-124">provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="value-property-example"></a><span data-ttu-id="2f6a4-125">Przykład właściwości wartości</span><span class="sxs-lookup"><span data-stu-id="2f6a4-125">Value property example</span></span>  
 <span data-ttu-id="2f6a4-126">Możesz użyć właściwości, <xref:System.Xml.Linq.XElement.Value%2A> Aby pobrać zawartość elementu:</span><span class="sxs-lookup"><span data-stu-id="2f6a4-126">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 <span data-ttu-id="2f6a4-127">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="2f6a4-127">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="element-might-not-exist-example"></a><span data-ttu-id="2f6a4-128">Element może nie istnieć przykład</span><span class="sxs-lookup"><span data-stu-id="2f6a4-128">Element might not exist example</span></span>
 <span data-ttu-id="2f6a4-129">Czasami próbujesz pobrać wartość elementu, mimo że nie masz pewności, czy istnieje.</span><span class="sxs-lookup"><span data-stu-id="2f6a4-129">Sometimes you try to retrieve the value of an element even though you're not sure if it exists.</span></span> <span data-ttu-id="2f6a4-130">W tym przypadku, gdy przypiszesz element rzutowany do typu referencyjnego nullable lub typu wartości null, jeśli element nie istnieje, przypisana zmienna jest ustawiona na `null` .</span><span class="sxs-lookup"><span data-stu-id="2f6a4-130">In this case, when you assign the casted element to a nullable reference type or nullable value type, if the element does not exist, the assigned variable is set to `null`.</span></span> <span data-ttu-id="2f6a4-131">Poniższy kod pokazuje, że gdy element może lub nie istnieje, łatwiej jest użyć rzutowania niż w celu użycia <xref:System.Xml.Linq.XElement.Value%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="2f6a4-131">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "child 1 content"),  
    new XElement("Child2", "2")  
);  
  
// The following assignments show why it is easier to use  
// casting when the element might or might not exist.  
  
string c1 = (string)root.Element("Child1");  
Console.WriteLine("c1:{0}", c1 == null ? "element does not exist" : c1);  
  
int? c2 = (int?)root.Element("Child2");  
Console.WriteLine("c2:{0}", c2 == null ? "element does not exist" : c2.ToString());  
  
string c3 = (string)root.Element("Child3");  
Console.WriteLine("c3:{0}", c3 == null ? "element does not exist" : c3);  
  
int? c4 = (int?)root.Element("Child4");  
Console.WriteLine("c4:{0}", c4 == null ? "element does not exist" : c4.ToString());  
  
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
Console.WriteLine("v1:{0}", v1 == null ? "element does not exist" : v1);  
  
XElement e2 = root.Element("Child2");  
int? v2;  
if (e2 == null)  
    v2 = null;  
else  
    v2 = Int32.Parse(e2.Value);  
Console.WriteLine("v2:{0}", v2 == null ? "element does not exist" : v2.ToString());  
  
XElement e3 = root.Element("Child3");  
string v3;  
if (e3 == null)  
    v3 = null;  
else  
    v3 = e3.Value;  
Console.WriteLine("v3:{0}", v3 == null ? "element does not exist" : v3);  
  
XElement e4 = root.Element("Child4");  
int? v4;  
if (e4 == null)  
    v4 = null;  
else  
    v4 = Int32.Parse(e4.Value);  
Console.WriteLine("v4:{0}", v4 == null ? "element does not exist" : v4.ToString());  
```  
  
 <span data-ttu-id="2f6a4-132">Ten kod spowoduje wygenerowanie następujących danych wyjściowych:</span><span class="sxs-lookup"><span data-stu-id="2f6a4-132">This code produces the following output:</span></span>  
  
```output  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 <span data-ttu-id="2f6a4-133">Ogólnie rzecz biorąc, można napisać łatwiejszy kod podczas używania rzutowania do pobrania zawartości elementów i atrybutów.</span><span class="sxs-lookup"><span data-stu-id="2f6a4-133">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f6a4-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2f6a4-134">See also</span></span>

- [<span data-ttu-id="2f6a4-135">Osie LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="2f6a4-135">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
