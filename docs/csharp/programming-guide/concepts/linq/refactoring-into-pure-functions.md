---
title: Refaktoryzacja do czystych funkcji (C#)
description: Dowiedz się, jak Refaktoryzacja kodu przy użyciu czystych funkcji. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
ms.assetid: 2944a0d4-fd33-4e2e-badd-abb0f9be2fcc
ms.openlocfilehash: cc5dd26923e2edaed34c8f1b742b3dfa1e935e68
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87300231"
---
# <a name="refactoring-into-pure-functions-c"></a><span data-ttu-id="7b52d-104">Refaktoryzacja do czystych funkcji (C#)</span><span class="sxs-lookup"><span data-stu-id="7b52d-104">Refactoring Into Pure Functions (C#)</span></span>

<span data-ttu-id="7b52d-105">Ważnym aspektem czystych transformacji funkcjonalnych jest uczenie się, jak kod refaktoryzacji przy użyciu czystych funkcji.</span><span class="sxs-lookup"><span data-stu-id="7b52d-105">An important aspect of pure functional transformations is learning how to refactor code using pure functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b52d-106">Wspólna Nomenklatura w programowaniu funkcjonalnym polega na tym, że programy refaktoryzacji używają czystych funkcji.</span><span class="sxs-lookup"><span data-stu-id="7b52d-106">The common nomenclature in functional programming is that you refactor programs using pure functions.</span></span> <span data-ttu-id="7b52d-107">W Visual Basic i C++ jest to zgodne z użyciem funkcji w odpowiednich językach.</span><span class="sxs-lookup"><span data-stu-id="7b52d-107">In Visual Basic and C++, this aligns with the use of functions in the respective languages.</span></span> <span data-ttu-id="7b52d-108">Jednak w języku C# funkcje są nazywane metodami.</span><span class="sxs-lookup"><span data-stu-id="7b52d-108">However, in C#, functions are called methods.</span></span> <span data-ttu-id="7b52d-109">Na potrzeby tej dyskusji czysta funkcja jest implementowana jako metoda w języku C#.</span><span class="sxs-lookup"><span data-stu-id="7b52d-109">For the purposes of this discussion, a pure function is implemented as a method in C#.</span></span>  
  
 <span data-ttu-id="7b52d-110">Jak wspomniano wcześniej w tej sekcji, czysta funkcja ma dwie przydatne cechy:</span><span class="sxs-lookup"><span data-stu-id="7b52d-110">As noted previously in this section, a pure function has two useful characteristics:</span></span>  
  
- <span data-ttu-id="7b52d-111">Nie ma żadnych efektów ubocznych.</span><span class="sxs-lookup"><span data-stu-id="7b52d-111">It has no side effects.</span></span> <span data-ttu-id="7b52d-112">Funkcja nie zmienia żadnych zmiennych ani danych dowolnego typu poza funkcją.</span><span class="sxs-lookup"><span data-stu-id="7b52d-112">The function does not change any variables or the data of any type outside of the function.</span></span>  
  
- <span data-ttu-id="7b52d-113">Jest ona spójna.</span><span class="sxs-lookup"><span data-stu-id="7b52d-113">It is consistent.</span></span> <span data-ttu-id="7b52d-114">Mając ten sam zestaw danych wejściowych, zawsze zwróci tę samą wartość wyjściową.</span><span class="sxs-lookup"><span data-stu-id="7b52d-114">Given the same set of input data, it will always return the same output value.</span></span>  
  
 <span data-ttu-id="7b52d-115">Jednym ze sposobów przejścia do programowania funkcjonalnego jest Refaktoryzacja istniejącego kodu w celu wyeliminowania zbędnych efektów ubocznych i zewnętrznych zależności.</span><span class="sxs-lookup"><span data-stu-id="7b52d-115">One way of transitioning to functional programming is to refactor existing code to eliminate unnecessary side effects and external dependencies.</span></span> <span data-ttu-id="7b52d-116">W ten sposób można utworzyć czystą wersję funkcji istniejącego kodu.</span><span class="sxs-lookup"><span data-stu-id="7b52d-116">In this way, you can create pure function versions of existing code.</span></span>  
  
 <span data-ttu-id="7b52d-117">W tym temacie omówiono czystą funkcję i jej znaczenie.</span><span class="sxs-lookup"><span data-stu-id="7b52d-117">This topic discusses what a pure function is and what it is not.</span></span> <span data-ttu-id="7b52d-118">[Samouczek: manipulowanie zawartością w samouczku dokumentu WordprocessingML (C#)](./shape-of-wordprocessingml-documents.md) pokazuje, jak manipulować dokumentem WordprocessingML i zawiera dwa przykłady sposobu refaktoryzacji przy użyciu czystej funkcji.</span><span class="sxs-lookup"><span data-stu-id="7b52d-118">The [Tutorial: Manipulating Content in a WordprocessingML Document (C#)](./shape-of-wordprocessingml-documents.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.</span></span>  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a><span data-ttu-id="7b52d-119">Eliminowanie efektów ubocznych i zależności zewnętrznych</span><span class="sxs-lookup"><span data-stu-id="7b52d-119">Eliminating Side Effects and External Dependencies</span></span>  
 <span data-ttu-id="7b52d-120">Poniższe przykłady różnią się dwoma nieczystymi funkcjami i czystą funkcją.</span><span class="sxs-lookup"><span data-stu-id="7b52d-120">The following examples contrast two non-pure functions and a pure function.</span></span>  
  
### <a name="non-pure-function-that-changes-a-class-member"></a><span data-ttu-id="7b52d-121">Nieczysta funkcja, która zmienia element członkowski klasy</span><span class="sxs-lookup"><span data-stu-id="7b52d-121">Non-Pure Function that Changes a Class Member</span></span>  
 <span data-ttu-id="7b52d-122">W poniższym kodzie `HyphenatedConcat` Funkcja nie jest czystą funkcją, ponieważ modyfikuje `aMember` element członkowski danych w klasie:</span><span class="sxs-lookup"><span data-stu-id="7b52d-122">In the following code, the `HyphenatedConcat` function is not a pure function, because it modifies the `aMember` data member in the class:</span></span>  
  
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
  
 <span data-ttu-id="7b52d-123">Ten kod spowoduje wygenerowanie następujących danych wyjściowych:</span><span class="sxs-lookup"><span data-stu-id="7b52d-123">This code produces the following output:</span></span>  
  
```output  
StringOne-StringTwo  
```  
  
 <span data-ttu-id="7b52d-124">Należy zauważyć, że nie ma znaczenia, czy modyfikowane dane mają dostęp, czy też jest członkiem `public` `private` `static` lub wystąpieniem.</span><span class="sxs-lookup"><span data-stu-id="7b52d-124">Note that it is irrelevant whether the data being modified has `public` or `private` access, or is a `static` member or an instance member.</span></span> <span data-ttu-id="7b52d-125">Czysta funkcja nie zmienia żadnych danych poza funkcją.</span><span class="sxs-lookup"><span data-stu-id="7b52d-125">A pure function does not change any data outside of the function.</span></span>  
  
### <a name="non-pure-function-that-changes-an-argument"></a><span data-ttu-id="7b52d-126">Nieczysta funkcja, która zmienia argument</span><span class="sxs-lookup"><span data-stu-id="7b52d-126">Non-Pure Function that Changes an Argument</span></span>  
 <span data-ttu-id="7b52d-127">Ponadto następująca wersja tej samej funkcji nie jest czysta, ponieważ modyfikuje zawartość jej parametru, `sb` .</span><span class="sxs-lookup"><span data-stu-id="7b52d-127">Furthermore, the following version of this same function is not pure because it modifies the contents of its parameter, `sb`.</span></span>  
  
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
  
 <span data-ttu-id="7b52d-128">Ta wersja programu daje te same dane wyjściowe co pierwsza wersja, ponieważ `HyphenatedConcat` Funkcja zmieniła wartość (stan) pierwszego parametru przez wywołanie <xref:System.Text.StringBuilder.Append%2A> funkcji członkowskiej.</span><span class="sxs-lookup"><span data-stu-id="7b52d-128">This version of the program produces the same output as the first version, because the `HyphenatedConcat` function has changed the value (state) of its first parameter by invoking the <xref:System.Text.StringBuilder.Append%2A> member function.</span></span> <span data-ttu-id="7b52d-129">Należy zauważyć, że ta zmiana występuje pomimo tego faktu, który `HyphenatedConcat` używa przekazywania parametrów wywołania przez wartość.</span><span class="sxs-lookup"><span data-stu-id="7b52d-129">Note that this alteration occurs despite that fact that `HyphenatedConcat` uses call-by-value parameter passing.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7b52d-130">W przypadku typów referencyjnych, Jeśli przekażesz parametr według wartości, wynikiem jest kopia odwołania do obiektu, który jest przekazywany.</span><span class="sxs-lookup"><span data-stu-id="7b52d-130">For reference types, if you pass a parameter by value, it results in a copy of the reference to an object being passed.</span></span> <span data-ttu-id="7b52d-131">Ta kopia jest nadal skojarzona z tymi samymi danymi wystąpienia co oryginalne odwołanie (do momentu przypisania zmiennej odniesienia do nowego obiektu).</span><span class="sxs-lookup"><span data-stu-id="7b52d-131">This copy is still associated with the same instance data as the original reference (until the reference variable is assigned to a new object).</span></span> <span data-ttu-id="7b52d-132">Wywołanie przez odwołanie nie musi być wymagane do zmodyfikowania parametru przez funkcję.</span><span class="sxs-lookup"><span data-stu-id="7b52d-132">Call-by-reference is not necessarily required for a function to modify a parameter.</span></span>  
  
### <a name="pure-function"></a><span data-ttu-id="7b52d-133">Czysta funkcja</span><span class="sxs-lookup"><span data-stu-id="7b52d-133">Pure Function</span></span>  
<span data-ttu-id="7b52d-134">Ta Następna wersja programu pokazuje, jak zaimplementować `HyphenatedConcat` funkcję jako czystą funkcję.</span><span class="sxs-lookup"><span data-stu-id="7b52d-134">This next version of the program shows how to implement the `HyphenatedConcat` function as a pure function.</span></span>  
  
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
  
 <span data-ttu-id="7b52d-135">Ta wersja generuje ten sam wiersz danych wyjściowych: `StringOne-StringTwo` .</span><span class="sxs-lookup"><span data-stu-id="7b52d-135">Again, this version produces the same line of output: `StringOne-StringTwo`.</span></span> <span data-ttu-id="7b52d-136">Należy pamiętać, że aby zachować łączną wartość, jest ona przechowywana w zmiennej pośredniej `s2` .</span><span class="sxs-lookup"><span data-stu-id="7b52d-136">Note that to retain the concatenated value, it is stored in the intermediate variable `s2`.</span></span>  
  
 <span data-ttu-id="7b52d-137">Jednym z metod, które może być bardzo przydatne, jest zapisanie funkcji, które są w sposób nieczysty (to oznacza, że deklarują i modyfikują zmienne lokalne), ale są globalnie czyste.</span><span class="sxs-lookup"><span data-stu-id="7b52d-137">One approach that can be very useful is to write functions that are locally impure (that is, they declare and modify local variables) but are globally pure.</span></span> <span data-ttu-id="7b52d-138">Takie funkcje mają wiele pożądanych cech tworzenia, ale unikają niektórych bardziej zawiłeych idiomy programowania, takich jak korzystanie z rekursji, gdy pętla prosta osiągnie tę samą wartość.</span><span class="sxs-lookup"><span data-stu-id="7b52d-138">Such functions have many of the desirable composability characteristics, but avoid some of the more convoluted functional programming idioms, such as having to use recursion when a simple loop would accomplish the same thing.</span></span>  
  
## <a name="standard-query-operators"></a><span data-ttu-id="7b52d-139">Standardowe operatory zapytań</span><span class="sxs-lookup"><span data-stu-id="7b52d-139">Standard Query Operators</span></span>  
 <span data-ttu-id="7b52d-140">Ważną cechą standardowych operatorów zapytań jest zaimplementowanie ich jako czystych funkcji.</span><span class="sxs-lookup"><span data-stu-id="7b52d-140">An important characteristic of the standard query operators is that they are implemented as pure functions.</span></span>  
  
 <span data-ttu-id="7b52d-141">Aby uzyskać więcej informacji, zobacz [standardowe operatory zapytań — Omówienie (C#)](./standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7b52d-141">For more information, see [Standard Query Operators Overview (C#)](./standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b52d-142">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7b52d-142">See also</span></span>

- [<span data-ttu-id="7b52d-143">Wprowadzenie do czystych transformacji funkcjonalnych (C#)</span><span class="sxs-lookup"><span data-stu-id="7b52d-143">Introduction to Pure Functional Transformations (C#)</span></span>](./introduction-to-pure-functional-transformations.md)
- [<span data-ttu-id="7b52d-144">Programowanie funkcjonalne a programowanie bezwzględne (C#)</span><span class="sxs-lookup"><span data-stu-id="7b52d-144">Functional Programming vs. Imperative Programming (C#)</span></span>](./functional-programming-vs-imperative-programming.md)
