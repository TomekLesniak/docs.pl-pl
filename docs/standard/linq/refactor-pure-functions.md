---
title: Refaktoryzacja do czystych funkcji — LINQ to XML
description: Uzyskaj informacje na temat czystych funkcji i sposobu ich używania w kodzie refaktoryzacji.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 2944a0d4-fd33-4e2e-badd-abb0f9be2fcc
ms.openlocfilehash: 18418a1fc39bee9f08cbe92d42c842e3fc9e148a
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553774"
---
# <a name="refactor-into-pure-functions-linq-to-xml"></a><span data-ttu-id="abd10-103">Refaktoryzacja do czystych funkcji (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="abd10-103">Refactor into pure functions (LINQ to XML)</span></span>

<span data-ttu-id="abd10-104">Ważnym aspektem czystych transformacji funkcjonalnych jest uczenie się, jak kod refaktoryzacji przy użyciu czystych funkcji.</span><span class="sxs-lookup"><span data-stu-id="abd10-104">An important aspect of pure functional transformations is learning how to refactor code using pure functions.</span></span>

> [!NOTE]
> <span data-ttu-id="abd10-105">Wspólna Nomenklatura w programowaniu funkcjonalnym polega na tym, że programy refaktoryzacji używają czystych funkcji.</span><span class="sxs-lookup"><span data-stu-id="abd10-105">The common nomenclature in functional programming is that you refactor programs using pure functions.</span></span> <span data-ttu-id="abd10-106">W Visual Basic i C++ jest to zgodne z użyciem funkcji w odpowiednich językach.</span><span class="sxs-lookup"><span data-stu-id="abd10-106">In Visual Basic and C++, this aligns with the use of functions in the respective languages.</span></span> <span data-ttu-id="abd10-107">Jednak w języku C# funkcje są nazywane metodami.</span><span class="sxs-lookup"><span data-stu-id="abd10-107">However, in C#, functions are called methods.</span></span> <span data-ttu-id="abd10-108">Na potrzeby tej dyskusji czysta funkcja jest implementowana jako metoda w języku C#.</span><span class="sxs-lookup"><span data-stu-id="abd10-108">For the purposes of this discussion, a pure function is implemented as a method in C#.</span></span>

<span data-ttu-id="abd10-109">Jak wspomniano wcześniej w tej sekcji, czysta funkcja ma dwie przydatne cechy:</span><span class="sxs-lookup"><span data-stu-id="abd10-109">As noted previously in this section, a pure function has two useful characteristics:</span></span>

- <span data-ttu-id="abd10-110">Nie ma żadnych efektów ubocznych.</span><span class="sxs-lookup"><span data-stu-id="abd10-110">It has no side effects.</span></span> <span data-ttu-id="abd10-111">Funkcja nie zmienia żadnych zmiennych ani danych dowolnego typu poza funkcją.</span><span class="sxs-lookup"><span data-stu-id="abd10-111">The function doesn't change any variables or the data of any type outside of the function.</span></span>
- <span data-ttu-id="abd10-112">Jest ona spójna.</span><span class="sxs-lookup"><span data-stu-id="abd10-112">It's consistent.</span></span> <span data-ttu-id="abd10-113">Mając ten sam zestaw danych wejściowych, zawsze zwróci tę samą wartość wyjściową.</span><span class="sxs-lookup"><span data-stu-id="abd10-113">Given the same set of input data, it will always return the same output value.</span></span>

<span data-ttu-id="abd10-114">Jednym ze sposobów przejścia do programowania funkcjonalnego jest Refaktoryzacja istniejącego kodu w celu wyeliminowania zbędnych efektów ubocznych i zewnętrznych zależności.</span><span class="sxs-lookup"><span data-stu-id="abd10-114">One way of transitioning to functional programming is to refactor existing code to eliminate unnecessary side effects and external dependencies.</span></span> <span data-ttu-id="abd10-115">W ten sposób można utworzyć czystą wersję funkcji istniejącego kodu.</span><span class="sxs-lookup"><span data-stu-id="abd10-115">In this way, you can create pure function versions of existing code.</span></span>

<span data-ttu-id="abd10-116">W tym artykule opisano, co to jest czysta funkcja i czego nie.</span><span class="sxs-lookup"><span data-stu-id="abd10-116">This article discusses what a pure function is and what it's not.</span></span> <span data-ttu-id="abd10-117">[Samouczek: manipulowanie zawartością w samouczku dokumentu WordprocessingML](xml-shape-wordprocessingml-documents.md) pokazuje, jak manipulować dokumentem WordprocessingML i zawiera dwa przykłady sposobu refaktoryzacji przy użyciu czystej funkcji.</span><span class="sxs-lookup"><span data-stu-id="abd10-117">The [Tutorial: Manipulate content in a WordprocessingML document](xml-shape-wordprocessingml-documents.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.</span></span>

<span data-ttu-id="abd10-118">Poniższe przykłady różnią się dwoma nieczystymi funkcjami i czystą funkcją.</span><span class="sxs-lookup"><span data-stu-id="abd10-118">The following examples contrast two non-pure functions and a pure function.</span></span>

## <a name="example-implement-a-non-pure-function-that-changes-a-static-class-member"></a><span data-ttu-id="abd10-119">Przykład: Zaimplementuj nieczystą funkcję, która zmienia statyczną składową klasy</span><span class="sxs-lookup"><span data-stu-id="abd10-119">Example: Implement a non-pure function that changes a static class member</span></span>

<span data-ttu-id="abd10-120">W poniższym kodzie `HyphenatedConcat` Funkcja nie jest czystą funkcją, ponieważ modyfikuje `aMember` statyczną składową klasy:</span><span class="sxs-lookup"><span data-stu-id="abd10-120">In the following code, the `HyphenatedConcat` function isn't a pure function, because it modifies the `aMember` static class member:</span></span>

```csharp
public class Program
{
    private static string aMember = "StringOne";

    public static void HyphenatedConcat(string appendStr)
    {
        aMember += '-' + appendStr;
    }

    public static void Main()
    {
        HyphenatedConcat("StringTwo");
        Console.WriteLine(aMember);
    }
}
```

```vb
Module Module1
    Dim aMember As String = "StringOne"

    Public Sub HyphenatedConcat(ByVal appendStr As String)
        aMember = aMember & "-" & appendStr
    End Sub

    Sub Main()
        HyphenatedConcat("StringTwo")
        Console.WriteLine(aMember)
    End Sub
End Module
```

<span data-ttu-id="abd10-121">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="abd10-121">This example produces the following output:</span></span>

```output
StringOne-StringTwo
```

<span data-ttu-id="abd10-122">Należy zauważyć, że nie ma znaczenia, czy modyfikowane dane mają `public` lub mają `private` dostęp, czy jest członkiem `static` , `shared` członkiem lub wystąpieniem.</span><span class="sxs-lookup"><span data-stu-id="abd10-122">Note that it's irrelevant whether the data being modified has `public` or `private` access, or is a `static` member, `shared` member, or instance member.</span></span> <span data-ttu-id="abd10-123">Czysta funkcja nie zmienia żadnych danych poza funkcją.</span><span class="sxs-lookup"><span data-stu-id="abd10-123">A pure function doesn't change any data outside of the function.</span></span>

## <a name="example-implement-a-non-pure-function-that-changes-a-parameter"></a><span data-ttu-id="abd10-124">Przykład: Zaimplementuj nieczystą funkcję, która zmienia parametr</span><span class="sxs-lookup"><span data-stu-id="abd10-124">Example: Implement a non-pure function that changes a parameter</span></span>

<span data-ttu-id="abd10-125">Ponadto następująca wersja tej samej funkcji nie jest czysta, ponieważ modyfikuje zawartość jej parametru, `sb` .</span><span class="sxs-lookup"><span data-stu-id="abd10-125">Furthermore, the following version of this same function isn't pure because it modifies the contents of its parameter, `sb`.</span></span>

```csharp
public class Program
{
    public static void HyphenatedConcat(StringBuilder sb, String appendStr)
    {
        sb.Append('-' + appendStr);
    }

    public static void Main()
    {
        StringBuilder sb1 = new StringBuilder("StringOne");
        HyphenatedConcat(sb1, "StringTwo");
        Console.WriteLine(sb1);
    }
}
```

```vb
Module Module1
    Public Sub HyphenatedConcat(ByVal sb As StringBuilder, ByVal appendStr As String)
        sb.Append("-" & appendStr)
    End Sub

    Sub Main()
        Dim sb1 As StringBuilder = New StringBuilder("StringOne")
        HyphenatedConcat(sb1, "StringTwo")
        Console.WriteLine(sb1)
    End Sub
End Module
```

<span data-ttu-id="abd10-126">Ta wersja programu daje te same dane wyjściowe co pierwsza wersja, ponieważ `HyphenatedConcat` Funkcja zmieniła wartość (stan) pierwszego parametru przez wywołanie <xref:System.Text.StringBuilder.Append%2A> funkcji członkowskiej.</span><span class="sxs-lookup"><span data-stu-id="abd10-126">This version of the program produces the same output as the first version, because the `HyphenatedConcat` function has changed the value (state) of its first parameter by invoking the <xref:System.Text.StringBuilder.Append%2A> member function.</span></span> <span data-ttu-id="abd10-127">Należy zauważyć, że ta zmiana występuje pomimo faktu, który `HyphenatedConcat` używa przekazywania parametrów wywołania przez wartość.</span><span class="sxs-lookup"><span data-stu-id="abd10-127">Note that this alteration occurs despite the fact that `HyphenatedConcat` uses call-by-value parameter passing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="abd10-128">W przypadku typów referencyjnych, Jeśli przekażesz parametr według wartości, wynikiem jest kopia odwołania do obiektu, który jest przekazywany.</span><span class="sxs-lookup"><span data-stu-id="abd10-128">For reference types, if you pass a parameter by value, it results in a copy of the reference to an object being passed.</span></span> <span data-ttu-id="abd10-129">Ta kopia jest nadal skojarzona z tymi samymi danymi wystąpienia co oryginalne odwołanie (do momentu przypisania zmiennej odniesienia do nowego obiektu).</span><span class="sxs-lookup"><span data-stu-id="abd10-129">This copy is still associated with the same instance data as the original reference (until the reference variable is assigned to a new object).</span></span> <span data-ttu-id="abd10-130">Wywołanie przez odwołanie nie musi być wymagane do zmodyfikowania parametru przez funkcję.</span><span class="sxs-lookup"><span data-stu-id="abd10-130">Call-by-reference isn't necessarily required for a function to modify a parameter.</span></span>

## <a name="example-implement-a-pure-function"></a><span data-ttu-id="abd10-131">Przykład: Zaimplementuj czystą funkcję</span><span class="sxs-lookup"><span data-stu-id="abd10-131">Example: Implement a pure function</span></span>

<span data-ttu-id="abd10-132">Ta Następna wersja programu pokazuje, jak zaimplementować `HyphenatedConcat` funkcję jako czystą funkcję.</span><span class="sxs-lookup"><span data-stu-id="abd10-132">This next version of the program shows how to implement the `HyphenatedConcat` function as a pure function.</span></span>

```csharp
class Program
{
    public static string HyphenatedConcat(string s, string appendStr)
    {
        return (s + '-' + appendStr);
    }

    public static void Main(string[] args)
    {
        string s1 = "StringOne";
        string s2 = HyphenatedConcat(s1, "StringTwo");
        Console.WriteLine(s2);
    }
}
```

```vb
Module Module1
    Public Function HyphenatedConcat(ByVal s As String, ByVal appendStr As String) As String
        Return (s & "-" & appendStr)
    End Function

    Sub Main()
        Dim s1 As String = "StringOne"
        Dim s2 As String = HyphenatedConcat(s1, "StringTwo")
        Console.WriteLine(s2)
    End Sub
End Module
```

<span data-ttu-id="abd10-133">Ta wersja generuje ten sam wiersz danych wyjściowych: `StringOne-StringTwo` .</span><span class="sxs-lookup"><span data-stu-id="abd10-133">Again, this version produces the same line of output: `StringOne-StringTwo`.</span></span> <span data-ttu-id="abd10-134">Należy pamiętać, że aby zachować łączną wartość, jest ona przechowywana w zmiennej pośredniej `s2` .</span><span class="sxs-lookup"><span data-stu-id="abd10-134">Note that to retain the concatenated value, it's stored in the intermediate variable `s2`.</span></span>

<span data-ttu-id="abd10-135">Jednym z metod, które może być bardzo przydatne, jest zapisanie funkcji, które są w sposób nieczysty (to oznacza, że deklarują i modyfikują zmienne lokalne), ale są globalnie czyste.</span><span class="sxs-lookup"><span data-stu-id="abd10-135">One approach that can be very useful is to write functions that are locally impure (that is, they declare and modify local variables) but are globally pure.</span></span> <span data-ttu-id="abd10-136">Takie funkcje mają wiele pożądanych cech tworzenia, ale unikają niektórych bardziej zawiłeych idiomy programowania, takich jak korzystanie z rekursji, gdy pętla prosta osiągnie tę samą wartość.</span><span class="sxs-lookup"><span data-stu-id="abd10-136">Such functions have many of the desirable composability characteristics, but avoid some of the more convoluted functional programming idioms, such as having to use recursion when a simple loop would accomplish the same thing.</span></span>

## <a name="standard-query-operators"></a><span data-ttu-id="abd10-137">Standardowe operatory zapytań</span><span class="sxs-lookup"><span data-stu-id="abd10-137">Standard query operators</span></span>

<span data-ttu-id="abd10-138">Ważną cechą standardowych operatorów zapytań jest to, że są one implementowane jako funkcje czyste.</span><span class="sxs-lookup"><span data-stu-id="abd10-138">An important characteristic of the standard query operators is that they're implemented as pure functions.</span></span>

<span data-ttu-id="abd10-139">Aby uzyskać więcej informacji, zobacz [standardowe operatory zapytań — Omówienie (C#)](../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) i [standardowe operatory zapytań — Omówienie (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="abd10-139">For more information, see [Standard Query Operators Overview (C#)](../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) and [Standard Query Operators Overview (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="abd10-140">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="abd10-140">See also</span></span>

- [<span data-ttu-id="abd10-141">Wprowadzenie do czystych transformacji funkcjonalnych</span><span class="sxs-lookup"><span data-stu-id="abd10-141">Introduction to pure functional transformations</span></span>](introduction-pure-functional-transformations.md)
- [<span data-ttu-id="abd10-142">Programowanie funkcjonalne a programowanie bezwzględne</span><span class="sxs-lookup"><span data-stu-id="abd10-142">Functional programming vs. imperative programming</span></span>](functional-vs-imperative-programming.md)
