---
title: Zapytania skompilowane statycznie — LINQ to XML
description: Dowiedz się, w jaki sposób zapytania LINQ to XML osiągają zalety wydajności w porównaniu do XmlDocument, które są kompilowane statycznie.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 3bf558fe-0705-479d-86d4-00188f5fcf9c
ms.openlocfilehash: 53dd47247eae8802dcf8187d0e82eb1c8bead9f9
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553416"
---
# <a name="statically-compiled-queries-linq-to-xml"></a><span data-ttu-id="d63f8-103">Zapytania skompilowane statycznie (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="d63f8-103">Statically compiled queries (LINQ to XML)</span></span>

<span data-ttu-id="d63f8-104">Jedną z najważniejszych zalet wydajności LINQ to XML, w porównaniu z <xref:System.Xml.XmlDocument> , jest to, że zapytania w LINQ to XML są kompilowane statycznie, podczas gdy zapytania XPath muszą być interpretowane w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="d63f8-104">One of the most important performance advantages of LINQ to XML, as compared to <xref:System.Xml.XmlDocument>, is that queries in LINQ to XML are statically compiled, whereas XPath queries must be interpreted at run time.</span></span> <span data-ttu-id="d63f8-105">Ta funkcja jest wbudowana w LINQ to XML, więc nie trzeba wykonywać dodatkowych czynności, aby korzystać z niej, ale warto zrozumieć rozróżnienie podczas wybierania dwóch technologii.</span><span class="sxs-lookup"><span data-stu-id="d63f8-105">This feature is built into LINQ to XML, so you don't have to perform extra steps to take advantage of it, but it's helpful to understand the distinction when choosing between the two technologies.</span></span> <span data-ttu-id="d63f8-106">W tym artykule opisano różnicę.</span><span class="sxs-lookup"><span data-stu-id="d63f8-106">This article explains the difference.</span></span>

## <a name="statically-compiled-queries-vs-xpath"></a><span data-ttu-id="d63f8-107">Zapytania skompilowane statycznie a XPath</span><span class="sxs-lookup"><span data-stu-id="d63f8-107">Statically compiled queries vs. XPath</span></span>

<span data-ttu-id="d63f8-108">Poniższy przykład pokazuje, jak uzyskać elementy podrzędne o określonej nazwie i z atrybutem o określonej wartości.</span><span class="sxs-lookup"><span data-stu-id="d63f8-108">The following example shows how to get the descendant elements with a specified name, and with an attribute with a specified value.</span></span> <span data-ttu-id="d63f8-109">Równoważne wyrażenie XPath ma wartość `//Address[@Type='Shipping']` .</span><span class="sxs-lookup"><span data-stu-id="d63f8-109">The equivalent XPath expression is `//Address[@Type='Shipping']`.</span></span>

```csharp
XDocument po = XDocument.Load("PurchaseOrders.xml");

IEnumerable<XElement> list1 =
    from el in po.Descendants("Address")
    where (string)el.Attribute("Type") == "Shipping"
    select el;

foreach (XElement el in list1)
    Console.WriteLine(el);
```

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = From el In po.Descendants("Address")
            Where el.@Type = "Shipping"

For Each el In list1
    Console.WriteLine(el)
Next
```

<span data-ttu-id="d63f8-110">Wyrażenie zapytania w tym przykładzie jest ponownie zapisywane przez kompilator do składni zapytania opartej na metodzie.</span><span class="sxs-lookup"><span data-stu-id="d63f8-110">The query expression in this example is rewritten by the compiler to method-based query syntax.</span></span> <span data-ttu-id="d63f8-111">Poniższy przykład, który został zapisany w składni zapytania opartej na metodzie, daje takie same wyniki jak poprzedni:</span><span class="sxs-lookup"><span data-stu-id="d63f8-111">The following example, which is written in method-based query syntax, produces the same results as the previous one:</span></span>

```csharp
XDocument po = XDocument.Load("PurchaseOrders.xml");

IEnumerable<XElement> list1 =
    po
    .Descendants("Address")
    .Where(el => (string)el.Attribute("Type") == "Shipping");

foreach (XElement el in list1)
    Console.WriteLine(el);
```

 ```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 As IEnumerable(Of XElement) = po.Descendants("Address").Where(Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

<span data-ttu-id="d63f8-112"><xref:System.Linq.Enumerable.Where%2A>Metoda jest metodą rozszerzenia.</span><span class="sxs-lookup"><span data-stu-id="d63f8-112">The <xref:System.Linq.Enumerable.Where%2A> method is an extension method.</span></span> <span data-ttu-id="d63f8-113">Aby uzyskać więcej informacji, zobacz [metody rozszerzenia (Przewodnik programowania w języku C#)](../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="d63f8-113">For more information, see [Extension Methods (C# Programming Guide)](../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="d63f8-114">Ponieważ <xref:System.Linq.Enumerable.Where%2A> jest to metoda rozszerzająca, zapytanie powyżej zostało skompilowane tak, jakby było zapisywane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="d63f8-114">Because <xref:System.Linq.Enumerable.Where%2A> is an extension method, the query above is compiled as though it were written as follows:</span></span>

```csharp
XDocument po = XDocument.Load("PurchaseOrders.xml");

IEnumerable<XElement> list1 =
    System.Linq.Enumerable.Where(
        po.Descendants("Address"),
        el => (string)el.Attribute("Type") == "Shipping");

foreach (XElement el in list1)
    Console.WriteLine(el);
```

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

<span data-ttu-id="d63f8-115">Ten przykład daje dokładnie te same wyniki co dwa poprzednie przykłady.</span><span class="sxs-lookup"><span data-stu-id="d63f8-115">This example produces exactly the same results as the previous two examples.</span></span> <span data-ttu-id="d63f8-116">Ilustruje to fakt, że zapytania są efektywnie kompilowane na wywołania metod połączonych statycznie.</span><span class="sxs-lookup"><span data-stu-id="d63f8-116">This illustrates the fact that queries are effectively compiled into statically linked method calls.</span></span> <span data-ttu-id="d63f8-117">W połączeniu z odroczoną semantyką wykonywania iteratorów, zwiększa wydajność.</span><span class="sxs-lookup"><span data-stu-id="d63f8-117">This, combined with the deferred execution semantics of iterators, improves performance.</span></span> <span data-ttu-id="d63f8-118">Aby uzyskać więcej informacji o odroczonej semantyki wykonywania iteratorów, zobacz [odroczone wykonywanie i obliczanie z opóźnieniem](deferred-execution-lazy-evaluation.md).</span><span class="sxs-lookup"><span data-stu-id="d63f8-118">For more information about the deferred execution semantics of iterators, see [Deferred execution and lazy evaluation](deferred-execution-lazy-evaluation.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d63f8-119">Te przykłady są reprezentatywne dla kodu, który kompilator może napisać.</span><span class="sxs-lookup"><span data-stu-id="d63f8-119">These examples are representative of the code that the compiler might write.</span></span> <span data-ttu-id="d63f8-120">Rzeczywista implementacja może się nieco różnić od tych przykładów, ale wydajność będzie taka sama jak lub podobna do tych przykładów.</span><span class="sxs-lookup"><span data-stu-id="d63f8-120">The actual implementation might differ slightly from these examples, but the performance will be the same as, or similar to, these examples.</span></span>

## <a name="executing-xpath-expressions-with-xmldocument"></a><span data-ttu-id="d63f8-121">Wykonywanie wyrażeń XPath przy użyciu elementu XmlDocument</span><span class="sxs-lookup"><span data-stu-id="d63f8-121">Executing XPath expressions with XmlDocument</span></span>

<span data-ttu-id="d63f8-122">Poniższy przykład używa <xref:System.Xml.XmlDocument> , aby wykonać te same wyniki co w poprzednich przykładach:</span><span class="sxs-lookup"><span data-stu-id="d63f8-122">The following example uses <xref:System.Xml.XmlDocument> to accomplish the same results as the previous examples:</span></span>

```csharp
XmlReader reader = XmlReader.Create("PurchaseOrders.xml");
XmlDocument doc = new XmlDocument();
doc.Load(reader);
XmlNodeList nl = doc.SelectNodes(".//Address[@Type='Shipping']");
foreach (XmlNode n in nl)
    Console.WriteLine(n.OuterXml);
reader.Close();
```

```vb
Dim reader = Xml.XmlReader.Create("PurchaseOrders.xml")
Dim doc As New Xml.XmlDocument()
doc.Load(reader)
Dim nl As Xml.XmlNodeList = doc.SelectNodes(".//Address[@Type='Shipping']")
For Each n As Xml.XmlNode In nl
    Console.WriteLine(n.OuterXml)
Next
reader.Close()
```

<span data-ttu-id="d63f8-123">To zapytanie zwraca te same dane wyjściowe jak przykłady, które używają LINQ to XML; Jedyną różnicą jest to, że LINQ to XML wcięcia drukowanych danych XML, a <xref:System.Xml.XmlDocument> nie.</span><span class="sxs-lookup"><span data-stu-id="d63f8-123">This query returns the same output as the examples that use LINQ to XML; the only difference is that LINQ to XML indents the printed XML, whereas <xref:System.Xml.XmlDocument> doesn't.</span></span>

<span data-ttu-id="d63f8-124">Jednak <xref:System.Xml.XmlDocument> podejście zwykle nie jest wykonywane, a LINQ to XML, ponieważ <xref:System.Xml.XmlNode.SelectNodes%2A> Metoda musi wykonać następujące czynności za każdym razem, gdy jest wywoływana:</span><span class="sxs-lookup"><span data-stu-id="d63f8-124">However, the <xref:System.Xml.XmlDocument> approach generally doesn't perform as well as LINQ to XML, because the <xref:System.Xml.XmlNode.SelectNodes%2A> method must do the following every time it's called:</span></span>

- <span data-ttu-id="d63f8-125">Przeanalizuj ciąg zawierający wyrażenie XPath, dzieląc ciąg na tokeny.</span><span class="sxs-lookup"><span data-stu-id="d63f8-125">Parse the string that contains the XPath expression, breaking the string into tokens.</span></span>
- <span data-ttu-id="d63f8-126">Sprawdź poprawność tokenów, aby upewnić się, że wyrażenie XPath jest prawidłowe.</span><span class="sxs-lookup"><span data-stu-id="d63f8-126">Validate the tokens to make sure that the XPath expression is valid.</span></span>
- <span data-ttu-id="d63f8-127">Przekształć wyrażenie w wewnętrzne drzewo wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="d63f8-127">Translate the expression into an internal expression tree.</span></span>
- <span data-ttu-id="d63f8-128">Wykonaj iterację węzłów, odpowiednio wybierając węzły dla zestawu wyników na podstawie oceny wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="d63f8-128">Iterate through the nodes, appropriately selecting the nodes for the result set based on the evaluation of the expression.</span></span>

<span data-ttu-id="d63f8-129">Jest to znacznie więcej niż pracy wykonanej przez odpowiednie LINQ to XML zapytanie.</span><span class="sxs-lookup"><span data-stu-id="d63f8-129">This is significantly more than the work done by the corresponding LINQ to XML query.</span></span> <span data-ttu-id="d63f8-130">Określona różnica wydajności różni się w zależności od różnych typów zapytań, ale w ogólnych zapytaniach LINQ to XML wykonuje mniej pracy i w związku z tym wykonuje lepsze, niż ocenianie wyrażeń XPath przy użyciu <xref:System.Xml.XmlDocument> .</span><span class="sxs-lookup"><span data-stu-id="d63f8-130">The specific performance difference varies for different types of queries, but in general LINQ to XML queries do less work, and therefore perform better, than evaluating XPath expressions using <xref:System.Xml.XmlDocument>.</span></span>
