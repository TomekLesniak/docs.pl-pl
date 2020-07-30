---
title: Jak napisać zapytanie, które znajduje elementy na podstawie kontekstu (C#)
description: Dowiedz się, jak napisać zapytanie, które znajdzie elementy na podstawie kontekstu. Zobacz przykłady kodu i wyświetlaj dodatkowe zasoby.
ms.date: 07/20/2015
ms.assetid: 3ff79ef0-fc8b-42fe-8cc0-10dc32b06b4e
ms.openlocfilehash: 64f09a41c2c1d01b0be8f776461f9be9df9ecb5f
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303195"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-c"></a><span data-ttu-id="0abc9-104">Jak napisać zapytanie, które znajduje elementy na podstawie kontekstu (C#)</span><span class="sxs-lookup"><span data-stu-id="0abc9-104">How to write a query that finds elements based on context (C#)</span></span>
<span data-ttu-id="0abc9-105">Czasami może być konieczne zapisanie zapytania, które wybiera elementy na podstawie ich kontekstu.</span><span class="sxs-lookup"><span data-stu-id="0abc9-105">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="0abc9-106">Można filtrować na podstawie poprzedzających lub następujących elementów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="0abc9-106">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="0abc9-107">Można filtrować na podstawie elementów podrzędnych lub nadrzędnych.</span><span class="sxs-lookup"><span data-stu-id="0abc9-107">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="0abc9-108">Można to zrobić przez zapisanie zapytania i użycie wyników zapytania w `where` klauzuli.</span><span class="sxs-lookup"><span data-stu-id="0abc9-108">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="0abc9-109">Jeśli konieczne jest pierwsze przetestowanie na wartość null, a następnie przetestowanie wartości, bardziej wygodne jest wykonanie zapytania w `let` klauzuli, a następnie użycie wyników w `where` klauzuli.</span><span class="sxs-lookup"><span data-stu-id="0abc9-109">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0abc9-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="0abc9-110">Example</span></span>  
 <span data-ttu-id="0abc9-111">W poniższym przykładzie wybrano wszystkie `p` elementy, które są bezpośrednio następuje po `ul` elemencie.</span><span class="sxs-lookup"><span data-stu-id="0abc9-111">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants("p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name.LocalName == "ul"  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="0abc9-112">Ten kod spowoduje wygenerowanie następujących danych wyjściowych:</span><span class="sxs-lookup"><span data-stu-id="0abc9-112">This code produces the following output:</span></span>  
  
```output  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="0abc9-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="0abc9-113">Example</span></span>  
 <span data-ttu-id="0abc9-114">W poniższym przykładzie pokazano to samo zapytanie dla kodu XML, który znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="0abc9-114">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="0abc9-115">Aby uzyskać więcej informacji, zobacz temat [przestrzenie nazw — omówienie (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0abc9-115">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
XNamespace ad = "http://www.adatum.com";  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants(ad + "p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name == ad.GetName("ul")  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="0abc9-116">Ten kod spowoduje wygenerowanie następujących danych wyjściowych:</span><span class="sxs-lookup"><span data-stu-id="0abc9-116">This code produces the following output:</span></span>  
  
```output  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="0abc9-117">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0abc9-117">See also</span></span>

- <xref:System.Xml.Linq.XElement.Parse%2A>
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>
- <xref:System.Linq.Enumerable.FirstOrDefault%2A>
