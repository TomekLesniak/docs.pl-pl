---
title: Zakres domyślnych przestrzeni nazw — LINQ to XML
description: Domyślne przestrzenie nazw, które są reprezentowane w drzewie XML, nie są w zakresie dla zapytań. Poniżej znajdują się odpowiednie i nieprawidłowe sposoby wykonywania zapytań.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: fe826236-830f-457a-9027-7ad62c909fae
ms.openlocfilehash: 105309a70e5fbf48c4e595d4064b11fe0378f81e
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553828"
---
# <a name="scope-of-default-namespaces-linq-to-xml"></a><span data-ttu-id="49649-104">Zakres domyślnych przestrzeni nazw (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="49649-104">Scope of default namespaces (LINQ to XML)</span></span>

<span data-ttu-id="49649-105">Domyślne przestrzenie nazw, które są reprezentowane w drzewie XML, nie są w zakresie dla zapytań.</span><span class="sxs-lookup"><span data-stu-id="49649-105">Default namespaces as represented in the XML tree aren't in scope for queries.</span></span> <span data-ttu-id="49649-106">Jeśli masz kod XML, który znajduje się w domyślnym obszarze nazw, musisz połączyć przestrzeń nazw z lokalną nazwą, aby nazwa kwalifikowana była używana w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="49649-106">If you have XML that's in a default namespace, you must combine a namespace with the local name to make a qualified name to be used in the query.</span></span>

<span data-ttu-id="49649-107">Typowy błąd podczas wykonywania zapytania w drzewie XML zawierającym domyślną przestrzeń nazw polega na zapisaniu zapytania, tak jakby plik XML nie był w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="49649-107">A common mistake in querying an XML tree that has a default namespace is to write the query as if the XML weren't in a namespace.</span></span> <span data-ttu-id="49649-108">Pierwszy przykład przedstawia typowe niewłaściwe zapytanie dotyczące domyślnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="49649-108">The first example shows a typical improper query of a default namespace.</span></span> <span data-ttu-id="49649-109">Drugi pokazuje prawidłowe zapytanie.</span><span class="sxs-lookup"><span data-stu-id="49649-109">The second shows a proper query.</span></span>

## <a name="example-improper-query-of-xml-in-a-namespace"></a><span data-ttu-id="49649-110">Przykład: nieprawidłowe zapytanie XML w przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="49649-110">Example: Improper query of XML in a namespace</span></span>

<span data-ttu-id="49649-111">Ten przykład pokazuje tworzenie XML w przestrzeni nazw i niewłaściwe zapytanie zwracające pusty zestaw wyników.</span><span class="sxs-lookup"><span data-stu-id="49649-111">This example shows the creation of XML in a namespace, and an improper query that returns an empty result set.</span></span>

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

<span data-ttu-id="49649-112">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="49649-112">This example produces the following output:</span></span>

```output
Result set follows:
End of result set
```

## <a name="example--proper-query-of-xml-in-a-namespace"></a><span data-ttu-id="49649-113">Przykład: prawidłowe zapytanie XML w przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="49649-113">Example:  Proper query of XML in a namespace</span></span>

<span data-ttu-id="49649-114">Ten przykład pokazuje tworzenie kodu XML w przestrzeni nazw i prawidłowe zapytanie.</span><span class="sxs-lookup"><span data-stu-id="49649-114">This example shows the creation of XML in a namespace, and a proper query.</span></span>

<span data-ttu-id="49649-115">W języku C# poprawne podejście polega na zadeklarowaniu i zainicjowaniu <xref:System.Xml.Linq.XNamespace> obiektu oraz użyciu go podczas określania <xref:System.Xml.Linq.XName> obiektów.</span><span class="sxs-lookup"><span data-stu-id="49649-115">In C#, the correct approach is to declare and initialize an <xref:System.Xml.Linq.XNamespace> object, and to use it when specifying <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="49649-116">W tym przypadku argument <xref:System.Xml.Linq.XContainer.Elements%2A> metody jest <xref:System.Xml.Linq.XName> obiektem.</span><span class="sxs-lookup"><span data-stu-id="49649-116">In this case, the argument to the <xref:System.Xml.Linq.XContainer.Elements%2A> method is an <xref:System.Xml.Linq.XName> object.</span></span>

<span data-ttu-id="49649-117">Poprawna Metoda korzystania z Visual Basic polega na zadeklarowaniu i zainicjowaniu globalnej domyślnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="49649-117">The correct approach when using Visual Basic is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="49649-118">Spowoduje to umieszczenie wszystkich właściwości XML w domyślnej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="49649-118">This places all XML properties in the default namespace.</span></span>

<span data-ttu-id="49649-119">Oto kod:</span><span class="sxs-lookup"><span data-stu-id="49649-119">Here is the code:</span></span>

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
            Console.WriteLine(el.Value)
        Next
        Console.WriteLine("End of result set")
    End Sub
End Module
```

<span data-ttu-id="49649-120">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="49649-120">This example produces the following output:</span></span>

```output
Result set follows:
1
2
3
End of result set
```

## <a name="see-also"></a><span data-ttu-id="49649-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="49649-121">See also</span></span>

- [<span data-ttu-id="49649-122">Przegląd przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="49649-122">Namespaces overview</span></span>](namespaces-overview.md)
