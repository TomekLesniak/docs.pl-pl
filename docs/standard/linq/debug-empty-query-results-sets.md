---
title: Jak debugować puste zestawy wyników zapytania — LINQ to XML
description: Podczas wykonywania zapytania w drzewie XML w domyślnej przestrzeni nazw, unikaj typowego błędu zapytania, tak jakby kod XML nie był w przestrzeni nazw.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: b569f0dc-425e-45a6-acbf-770fb761c981
ms.openlocfilehash: 3320763fffe77ddd6ca4c78e77629ec0805e4290
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553488"
---
# <a name="how-to-debug-empty-query-results-sets-linq-to-xml"></a><span data-ttu-id="4aa22-103">Jak debugować puste zestawy wyników zapytania (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="4aa22-103">How to debug empty query results sets (LINQ to XML)</span></span>

<span data-ttu-id="4aa22-104">Jednym z najczęstszych problemów związanych z kwerendą drzewa XML jest to, że jeśli drzewo XML ma domyślną przestrzeń nazw, deweloper czasami zapisuje zapytanie tak, jakby kod XML nie był w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="4aa22-104">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>

<span data-ttu-id="4aa22-105">Pierwszy zestaw przykładów w tym artykule przedstawia typowy sposób ładowania kodu XML w domyślnej przestrzeni nazw, a następnie zapytanie nieprawidłowo.</span><span class="sxs-lookup"><span data-stu-id="4aa22-105">The first set of examples in this article shows a typical way that XML in a default namespace is loaded, and then queried improperly.</span></span>

<span data-ttu-id="4aa22-106">Drugi zestaw przykładów pokazuje niezbędne poprawki, aby można było zbadać kod XML w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="4aa22-106">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>

<span data-ttu-id="4aa22-107">Aby uzyskać więcej informacji, zobacz [Omówienie przestrzeni nazw](namespaces-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4aa22-107">For more information, see [Namespaces overview](namespaces-overview.md).</span></span>

## <a name="example-an-improper-query-on-xml-in-a-namespace"></a><span data-ttu-id="4aa22-108">Przykład: nieprawidłowe zapytanie dotyczące kodu XML w przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="4aa22-108">Example: An improper query on XML in a namespace</span></span>

<span data-ttu-id="4aa22-109">Ten przykład pokazuje tworzenie XML w przestrzeni nazw i zapytanie zwracające pusty zestaw wyników.</span><span class="sxs-lookup"><span data-stu-id="4aa22-109">This example shows creation of XML in a namespace, and a query that returns an empty result set.</span></span>

```csharp
XElement root = XElement.Parse(
@"<Root xmlns='http://www.adventure-works.com'>
    <Child>1</Child>
    <Child>2</Child>
    <Child>3</Child>
    <AnotherChild>4</AnotherChild>
    <AnotherChild>5</AnotherChild>
    <AnotherChild>6</AnotherChild>
</Root>");
IEnumerable<XElement> c1 =
    from el in root.Elements("Child")
    select el;
Console.WriteLine("Result set follows:");
foreach (XElement el in c1)
    Console.WriteLine((int)el);
Console.WriteLine("End of result set");
```

```vb
Dim root As XElement = _
    <Root xmlns='http://www.adventure-works.com'>
        <Child>1</Child>
        <Child>2</Child>
        <Child>3</Child>
        <AnotherChild>4</AnotherChild>
        <AnotherChild>5</AnotherChild>
        <AnotherChild>6</AnotherChild>
    </Root>
Dim c1 As IEnumerable(Of XElement) = _
        From el In root.<Child> _
        Select el
Console.WriteLine("Result set follows:")
For Each el As XElement In c1
    Console.WriteLine(el.Value)
Next
Console.WriteLine("End of result set")
```

<span data-ttu-id="4aa22-110">Przykład generuje ten wynik:</span><span class="sxs-lookup"><span data-stu-id="4aa22-110">The example produces this result:</span></span>

```output
Result set follows:
End of result set
```

## <a name="example-a-proper-query-on-xml-in-a-namespace"></a><span data-ttu-id="4aa22-111">Przykład: prawidłowe zapytanie dotyczące kodu XML w przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="4aa22-111">Example: A proper query on XML in a namespace</span></span>

<span data-ttu-id="4aa22-112">Ten przykład pokazuje tworzenie kodu XML w przestrzeni nazw oraz zakodowane prawidłowo zapytanie.</span><span class="sxs-lookup"><span data-stu-id="4aa22-112">This example shows creation of XML in a namespace, and a query that's  coded properly.</span></span>

<span data-ttu-id="4aa22-113">Rozwiązaniem jest zadeklarowanie i zainicjowanie <xref:System.Xml.Linq.XNamespace> obiektu oraz użycie go podczas określania <xref:System.Xml.Linq.XName> obiektów.</span><span class="sxs-lookup"><span data-stu-id="4aa22-113">The solution is to declare and initialize an <xref:System.Xml.Linq.XNamespace> object, and to use it when specifying <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="4aa22-114">W tym przypadku argument <xref:System.Xml.Linq.XContainer.Elements%2A> metody jest <xref:System.Xml.Linq.XName> obiektem.</span><span class="sxs-lookup"><span data-stu-id="4aa22-114">In this case, the argument to the <xref:System.Xml.Linq.XContainer.Elements%2A> method is an <xref:System.Xml.Linq.XName> object.</span></span>

```csharp
XElement root = XElement.Parse(
@"<Root xmlns='http://www.adventure-works.com'>
    <Child>1</Child>
    <Child>2</Child>
    <Child>3</Child>
    <AnotherChild>4</AnotherChild>
    <AnotherChild>5</AnotherChild>
    <AnotherChild>6</AnotherChild>
</Root>");
XNamespace aw = "http://www.adventure-works.com";
IEnumerable<XElement> c1 =
    from el in root.Elements(aw + "Child")
    select el;
Console.WriteLine("Result set follows:");
foreach (XElement el in c1)
    Console.WriteLine((int)el);
Console.WriteLine("End of result set");
```

```vb
Imports <xmlns="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = _
            <Root xmlns='http://www.adventure-works.com'>
                <Child>1</Child>
                <Child>2</Child>
                <Child>3</Child>
                <AnotherChild>4</AnotherChild>
                <AnotherChild>5</AnotherChild>
                <AnotherChild>6</AnotherChild>
            </Root>
        Dim c1 As IEnumerable(Of XElement) = _
                From el In root.<Child> _
                Select el
        Console.WriteLine("Result set follows:")
        For Each el As XElement In c1
            Console.WriteLine(CInt(el))
        Next
        Console.WriteLine("End of result set")
    End Sub
End Module
```

<span data-ttu-id="4aa22-115">Przykład generuje ten wynik:</span><span class="sxs-lookup"><span data-stu-id="4aa22-115">The example produces this result:</span></span>

```output
Result set follows:
1
2
3
End of result set
```

## <a name="see-also"></a><span data-ttu-id="4aa22-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4aa22-116">See also</span></span>

- [<span data-ttu-id="4aa22-117">Zapytania podstawowe (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4aa22-117">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
