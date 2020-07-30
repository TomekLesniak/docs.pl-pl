---
title: Jak znaleźć elementy podrzędne elementu podrzędnego (XPath-LINQ to XML) (C#)
description: Dowiedz się, jak znaleźć elementy podrzędne elementu podrzędnego z określoną nazwą przy użyciu wyrażenia XPath.
ms.date: 07/20/2015
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
ms.openlocfilehash: b8e110abc2e0df99c3fdf6d2846c7cbbc4736c1a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303260"
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="a5c48-103">Jak znaleźć elementy podrzędne elementu podrzędnego (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="a5c48-103">How to find descendants of a child element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="a5c48-104">W tym temacie pokazano, jak uzyskać elementy podrzędne elementu podrzędnego o określonej nazwie.</span><span class="sxs-lookup"><span data-stu-id="a5c48-104">This topic shows how to get the descendant elements of a child element with a particular name.</span></span>  
  
 <span data-ttu-id="a5c48-105">Wyrażenie XPath:</span><span class="sxs-lookup"><span data-stu-id="a5c48-105">The XPath expression is:</span></span>  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a><span data-ttu-id="a5c48-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="a5c48-106">Example</span></span>  
 <span data-ttu-id="a5c48-107">Ten przykład symuluje problemy związane z wyodrębnianiem tekstu z reprezentacji XML dokumentu przetwarzania tekstów.</span><span class="sxs-lookup"><span data-stu-id="a5c48-107">This example simulates the problems of extracting text from an XML representation of a word processing document.</span></span> <span data-ttu-id="a5c48-108">Najpierw zaznacza wszystkie `Paragraph` elementy, a następnie wybiera wszystkie elementy `Text` zależne każdego `Paragraph` elementu.</span><span class="sxs-lookup"><span data-stu-id="a5c48-108">It first selects all `Paragraph` elements, and then it selects all `Text` descendant elements of each `Paragraph` element.</span></span> <span data-ttu-id="a5c48-109">Nie wybrano elementów potomnych `Text` `Comment` elementu.</span><span class="sxs-lookup"><span data-stu-id="a5c48-109">This doesn't select the descendant `Text` elements of the `Comment` element.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root>  
  <Paragraph>  
    <Text>This is the start of</Text>  
  </Paragraph>  
  <Comment>  
    <Text>This comment is not part of the paragraph text.</Text>  
  </Comment>  
  <Paragraph>  
    <Annotation Emphasis='true'>  
      <Text> a sentence.</Text>  
    </Annotation>  
  </Paragraph>  
  <Paragraph>  
    <Text>  This is a second sentence.</Text>  
  </Paragraph>  
</Root>");  
  
// LINQ to XML query  
string str1 =  
    root  
    .Elements("Paragraph")  
    .Descendants("Text")  
    .Select(s => s.Value)  
    .Aggregate(  
        new StringBuilder(),  
        (s, i) => s.Append(i),  
        s => s.ToString()  
    );  
  
// XPath expression  
string str2 =  
    ((IEnumerable)root.XPathEvaluate("./Paragraph//Text/text()"))  
    .Cast<XText>()  
    .Select(s => s.Value)  
    .Aggregate(  
        new StringBuilder(),  
        (s, i) => s.Append(i),  
        s => s.ToString()  
    );  
  
if (str1 == str2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(str2);  
```  
  
 <span data-ttu-id="a5c48-110">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="a5c48-110">This example produces the following output:</span></span>  
  
```output  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  