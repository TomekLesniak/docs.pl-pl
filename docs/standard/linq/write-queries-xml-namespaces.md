---
title: Jak pisać zapytania dotyczące kodu XML w przestrzeniach nazw — LINQ to XML
description: Aby napisać zapytanie dotyczące kodu XML, który znajduje się w przestrzeni nazw, należy użyć obiektów XName, które mają prawidłową przestrzeń nazw. Dowiedz się, jak to zrobić w języku C# i Visual Basic oraz jak tworzyć zapytania.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
ms.openlocfilehash: 7d2c765c30409b019bf4723b9161c577e2074c04
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553029"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-linq-to-xml"></a><span data-ttu-id="9b4b7-104">Jak pisać zapytania dotyczące kodu XML w przestrzeniach nazw (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="9b4b7-104">How to write queries on XML in namespaces (LINQ to XML)</span></span>

<span data-ttu-id="9b4b7-105">Aby napisać zapytanie dotyczące kodu XML, który znajduje się w przestrzeni nazw, należy użyć <xref:System.Xml.Linq.XName> obiektów, które mają prawidłową przestrzeń nazw.</span><span class="sxs-lookup"><span data-stu-id="9b4b7-105">To write a query on XML that's in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>

<span data-ttu-id="9b4b7-106">W przypadku języka C# najbardziej typowym podejściem jest zainicjowanie <xref:System.Xml.Linq.XNamespace> przy użyciu ciągu, który zawiera identyfikator URI, a następnie użycie przeciążenia operatora dodawania, aby połączyć przestrzeń nazw z nazwą lokalną.</span><span class="sxs-lookup"><span data-stu-id="9b4b7-106">For C#, the most common approach is to initialize an <xref:System.Xml.Linq.XNamespace> using a string that contains the URI, then use the addition operator overload to combine the namespace with the local name.</span></span>

<span data-ttu-id="9b4b7-107">W przypadku Visual Basic najbardziej typowym podejściem jest zdefiniowanie globalnej przestrzeni nazw, a następnie użycie literałów XML i właściwości XML, które używają globalnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="9b4b7-107">For Visual Basic, the most common approach is to define a global namespace, and then use XML literals and XML properties that use the global namespace.</span></span> <span data-ttu-id="9b4b7-108">Można zdefiniować globalną domyślną przestrzeń nazw, w której elementy case w literałach XML będą domyślnie w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="9b4b7-108">You can define a global default namespace, in which case elements in the XML literals will be in the namespace by default.</span></span> <span data-ttu-id="9b4b7-109">Alternatywnie można zdefiniować globalną przestrzeń nazw z prefiksem, a następnie użyć prefiksu zgodnie z wymaganiami w literałach XML i we właściwościach XML.</span><span class="sxs-lookup"><span data-stu-id="9b4b7-109">Alternatively, you can define a global namespace with a prefix, and then use the prefix as required in the XML literals and in XML properties.</span></span> <span data-ttu-id="9b4b7-110">Podobnie jak w przypadku innych form XML, atrybuty są zawsze domyślnie w żadnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="9b4b7-110">As with other forms of XML, attributes are always in no namespace by default.</span></span>

<span data-ttu-id="9b4b7-111">Pierwszy przykład w tym artykule pokazuje, jak utworzyć drzewo XML w domyślnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="9b4b7-111">The first example in this article shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="9b4b7-112">Drugi pokazuje, jak utworzyć drzewo XML w przestrzeni nazw z prefiksem.</span><span class="sxs-lookup"><span data-stu-id="9b4b7-112">The second shows how to create an XML tree in a namespace with a prefix.</span></span>

## <a name="example-create-a-tree-in-a-default-namespace-and-retrieve-elements"></a><span data-ttu-id="9b4b7-113">Przykład: Utwórz drzewo w domyślnej przestrzeni nazw i Pobierz elementy</span><span class="sxs-lookup"><span data-stu-id="9b4b7-113">Example: Create a tree in a default namespace and retrieve elements</span></span>

<span data-ttu-id="9b4b7-114">Poniższy przykład tworzy drzewo XML, który znajduje się w domyślnej przestrzeni nazw, a następnie pobiera kolekcję elementów.</span><span class="sxs-lookup"><span data-stu-id="9b4b7-114">The following example creates an XML tree that's in a default namespace, and then retrieves a collection of elements.</span></span>

```csharp
XNamespace aw = "http://www.adventure-works.com";
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
    from el in root.Elements(aw + "Child")
    select el;
foreach (XElement el in c1)
    Console.WriteLine((int)el);
```

```vb
Imports <xmlns="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = _
            <Root>
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
        For Each el As XElement In c1
            Console.WriteLine(el.Value)
        Next
    End Sub
End Module
```

<span data-ttu-id="9b4b7-115">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="9b4b7-115">This example produces the following output:</span></span>

```output
1
2
3
```

## <a name="example-create-a-tree-in-a-namespace-with-a-prefix-and-retrieve-elements"></a><span data-ttu-id="9b4b7-116">Przykład: Utwórz drzewo w przestrzeni nazw z prefiksem i Pobierz elementy</span><span class="sxs-lookup"><span data-stu-id="9b4b7-116">Example: Create a tree in a namespace with a prefix and retrieve elements</span></span>

<span data-ttu-id="9b4b7-117">W języku C# zapytania są pisane w taki sam sposób, niezależnie od tego, czy piszesz zapytania w drzewie XML, który używa przestrzeni nazw z prefiksem lub w drzewie XML z domyślną przestrzenią nazw.</span><span class="sxs-lookup"><span data-stu-id="9b4b7-117">In C#, you write queries in the same way regardless of whether you're writing queries on an XML tree that uses a namespace with a prefix or on an XML tree with a default namespace.</span></span>

<span data-ttu-id="9b4b7-118">Poniższy przykład tworzy drzewo XML, który znajduje się w przestrzeni nazw z prefiksem, a następnie pobiera kolekcję elementów.</span><span class="sxs-lookup"><span data-stu-id="9b4b7-118">The following example creates an XML tree that's in a namespace with a prefix, and then retrieves a collection of elements.</span></span>

```csharp
XNamespace aw = "http://www.adventure-works.com";
XElement root = XElement.Parse(
@"<aw:Root xmlns:aw='http://www.adventure-works.com'>
    <aw:Child>1</aw:Child>
    <aw:Child>2</aw:Child>
    <aw:Child>3</aw:Child>
    <aw:AnotherChild>4</aw:AnotherChild>
    <aw:AnotherChild>5</aw:AnotherChild>
    <aw:AnotherChild>6</aw:AnotherChild>
</aw:Root>");
IEnumerable<XElement> c1 =
    from el in root.Elements(aw + "Child")
    select el;
foreach (XElement el in c1)
    Console.WriteLine((int)el);
```

```vb
Imports <xmlns:aw="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = _
            <aw:Root>
                <aw:Child>1</aw:Child>
                <aw:Child>2</aw:Child>
                <aw:Child>3</aw:Child>
                <aw:AnotherChild>4</aw:AnotherChild>
                <aw:AnotherChild>5</aw:AnotherChild>
                <aw:AnotherChild>6</aw:AnotherChild>
            </aw:Root>
        Dim c1 As IEnumerable(Of XElement) = _
            From el In root.<aw:Child> _
            Select el
        For Each el As XElement In c1
            Console.WriteLine(CInt(el))
        Next
    End Sub
End Module
```

<span data-ttu-id="9b4b7-119">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="9b4b7-119">This example produces the following output:</span></span>

```output
1
2
3
```

## <a name="see-also"></a><span data-ttu-id="9b4b7-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9b4b7-120">See also</span></span>

- [<span data-ttu-id="9b4b7-121">Przegląd przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="9b4b7-121">Namespaces overview</span></span>](namespaces-overview.md)
