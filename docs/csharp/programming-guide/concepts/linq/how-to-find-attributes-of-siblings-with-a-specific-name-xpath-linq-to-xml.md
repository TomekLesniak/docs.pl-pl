---
title: Jak znaleźć atrybuty elementów równorzędnych o określonej nazwie (XPath-LINQ to XML) (C#)
description: Dowiedz się, jak znaleźć wszystkie atrybuty elementów równorzędnych węzła kontekstu. Przejrzyj przykład kodu, który używa przykładowego pliku XML.
ms.date: 07/20/2015
ms.assetid: c3133d64-523f-422d-8838-73d36b945ca0
ms.openlocfilehash: 12bba22c91fef92fc3383d028ff9dfb8bd3cfa3e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301700"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-c"></a><span data-ttu-id="0b384-104">Jak znaleźć atrybuty elementów równorzędnych o określonej nazwie (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0b384-104">How to find attributes of siblings with a specific name (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="0b384-105">W tym temacie pokazano, jak znaleźć wszystkie atrybuty elementów równorzędnych węzła kontekstu.</span><span class="sxs-lookup"><span data-stu-id="0b384-105">This topic shows how to find all attributes of the siblings of the context node.</span></span> <span data-ttu-id="0b384-106">W kolekcji są zwracane tylko atrybuty o określonej nazwie.</span><span class="sxs-lookup"><span data-stu-id="0b384-106">Only attributes with a specific name are returned in the collection.</span></span>  
  
 <span data-ttu-id="0b384-107">Wyrażenie XPath:</span><span class="sxs-lookup"><span data-stu-id="0b384-107">The XPath expression is:</span></span>  
  
 `../Book/@id`  
  
## <a name="example"></a><span data-ttu-id="0b384-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="0b384-108">Example</span></span>  
 <span data-ttu-id="0b384-109">Ten przykład najpierw odnajduje `Book` element, a następnie znajduje wszystkie elementy równorzędne o nazwie `Book` , a następnie znajduje wszystkie atrybuty o nazwie `id` .</span><span class="sxs-lookup"><span data-stu-id="0b384-109">This example first finds a `Book` element, and then finds all sibling elements named `Book`, and then finds all attributes named `id`.</span></span> <span data-ttu-id="0b384-110">Wynik jest kolekcją atrybutów.</span><span class="sxs-lookup"><span data-stu-id="0b384-110">The result is a collection of attributes.</span></span>  
  
 <span data-ttu-id="0b384-111">Ten przykład używa następującego dokumentu XML: [przykładowy plik XML: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0b384-111">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =
    books  
    .Root  
    .Element("Book");  
  
// LINQ to XML query  
IEnumerable<XAttribute> list1 =  
    from el in book.Parent.Elements("Book")  
    select el.Attribute("id");  
  
// XPath expression  
IEnumerable<XAttribute> list2 =  
  ((IEnumerable)book.XPathEvaluate("../Book/@id")).Cast<XAttribute>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XAttribute el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="0b384-112">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="0b384-112">This example produces the following output:</span></span>  
  
```output  
Results are identical  
id="bk101"  
id="bk102"  
```  
  