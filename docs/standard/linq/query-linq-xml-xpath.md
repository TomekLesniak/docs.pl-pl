---
title: Jak zbadać LINQ to XML przy użyciu XPath-LINQ to XML
description: Poznaj metody rozszerzające, które umożliwiają badanie drzewa XML przy użyciu XPath.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: ee5af263-4ab1-45e5-b792-33a3221b426d
ms.openlocfilehash: 8189bcdd38f9242a5890837633bbec4e7f2fc601
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553711"
---
# <a name="how-to-query-linq-to-xml-using-xpath-linq-to-xml"></a><span data-ttu-id="4b13c-103">Jak zbadać LINQ to XML przy użyciu XPath (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="4b13c-103">How to query LINQ to XML using XPath (LINQ to XML)</span></span>

<span data-ttu-id="4b13c-104">W tym artykule wprowadzono metody rozszerzające, które umożliwiają badanie drzewa XML przy użyciu XPath.</span><span class="sxs-lookup"><span data-stu-id="4b13c-104">This article introduces the extension methods that enable you to query an XML tree by using XPath.</span></span> <span data-ttu-id="4b13c-105">Aby uzyskać szczegółowe informacje na temat korzystania z tych metod rozszerzających, zobacz <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4b13c-105">For detailed information about using these extension methods, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>

> [!NOTE]
> <span data-ttu-id="4b13c-106">Chyba że masz bardzo konkretny powód wykonywania zapytań przy użyciu XPath, na przykład w przypadku użycia starszego kodu, używanie XPath z LINQ to XML nie jest zalecane.</span><span class="sxs-lookup"><span data-stu-id="4b13c-106">Unless you have a very specific reason for querying using XPath, such as extensive use of legacy code, using XPath with LINQ to XML isn't recommended.</span></span> <span data-ttu-id="4b13c-107">Zapytania XPath nie będą działać oraz LINQ to XML zapytań.</span><span class="sxs-lookup"><span data-stu-id="4b13c-107">XPath queries won't perform as well as LINQ to XML queries.</span></span>

## <a name="example"></a><span data-ttu-id="4b13c-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="4b13c-108">Example</span></span>

<span data-ttu-id="4b13c-109">Poniższy przykład tworzy małe drzewo XML i używa <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> do wybierania zestawu elementów.</span><span class="sxs-lookup"><span data-stu-id="4b13c-109">The following example creates a small XML tree and uses <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to select a set of elements.</span></span>

```csharp
XElement root = new XElement("Root",
    new XElement("Child1", 1),
    new XElement("Child1", 2),
    new XElement("Child1", 3),
    new XElement("Child2", 4),
    new XElement("Child2", 5),
    new XElement("Child2", 6)
);
IEnumerable<XElement> list = root.XPathSelectElements("./Child2");
foreach (XElement el in list)
    Console.WriteLine(el);
```

```vb
Dim root As XElement = _
    <Root>
        <Child1>1</Child1>
        <Child1>2</Child1>
        <Child1>3</Child1>
        <Child2>4</Child2>
        <Child2>5</Child2>
        <Child2>6</Child2>
    </Root>

Dim list As IEnumerable(Of XElement) = root.XPathSelectElements("./Child2")
For Each el As XElement In list
    Console.WriteLine(el)
Next
```

<span data-ttu-id="4b13c-110">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="4b13c-110">This example produces the following output:</span></span>

```xml
<Child2>4</Child2>
<Child2>5</Child2>
<Child2>6</Child2>
```
