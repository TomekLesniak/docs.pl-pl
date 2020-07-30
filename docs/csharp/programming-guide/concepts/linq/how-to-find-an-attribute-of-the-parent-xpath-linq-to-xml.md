---
title: Jak znaleźć atrybut elementu nadrzędnego (XPath-LINQ to XML) (C#)
description: Dowiedz się, jak znaleźć atrybut elementu nadrzędnego. Zobacz przykład kodu, który używa przykładowego dokumentu XML.
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 03344bb66f617970d9598c91366eb7d69514397a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303299"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="f734e-104">Jak znaleźć atrybut elementu nadrzędnego (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="f734e-104">How to find an attribute of the parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="f734e-105">W tym temacie pokazano, jak przejść do elementu nadrzędnego i znaleźć jego atrybut.</span><span class="sxs-lookup"><span data-stu-id="f734e-105">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="f734e-106">Wyrażenie XPath:</span><span class="sxs-lookup"><span data-stu-id="f734e-106">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="f734e-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="f734e-107">Example</span></span>

<span data-ttu-id="f734e-108">Ten przykład najpierw znajduje `Author` element.</span><span class="sxs-lookup"><span data-stu-id="f734e-108">This example first finds an `Author` element.</span></span> <span data-ttu-id="f734e-109">Następnie znajduje `id` atrybut elementu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="f734e-109">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="f734e-110">Ten przykład używa następującego dokumentu XML: [przykładowy plik XML: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f734e-110">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>

```csharp
XDocument books = XDocument.Load("Books.xml");

XElement author =
    books
    .Root
    .Element("Book")
    .Element("Author");

// LINQ to XML query
XAttribute att1 =
    author
    .Parent
    .Attribute("id");

// XPath expression
XAttribute att2 = ((IEnumerable)author.XPathEvaluate("../@id")).Cast<XAttribute>().First();

if (att1 == att2)
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
Console.WriteLine(att1);
```

<span data-ttu-id="f734e-111">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="f734e-111">This example produces the following output:</span></span>

```output
Results are identical
id="bk101"
```
