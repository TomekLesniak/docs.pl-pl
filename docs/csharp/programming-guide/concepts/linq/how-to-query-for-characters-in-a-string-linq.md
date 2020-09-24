---
title: Jak wykonać zapytanie o znaki w ciągu (LINQ) (C#)
description: Możesz badać ciąg jako sekwencję znaków w LINQ. Ten przykład w języku C# wysyła zapytanie do ciągu, aby określić liczbę cyfr, które zawiera.
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: 73288924d057e720a744b853998a52437b9db481
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153940"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a><span data-ttu-id="4c2b1-104">Jak wykonać zapytanie o znaki w ciągu (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4c2b1-104">How to query for characters in a string (LINQ) (C#)</span></span>

<span data-ttu-id="4c2b1-105">Ponieważ <xref:System.String> Klasa implementuje <xref:System.Collections.Generic.IEnumerable%601> interfejs ogólny, dowolny ciąg może być badany jako sekwencja znaków.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-105">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="4c2b1-106">Nie jest to jednak powszechne użycie LINQ.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-106">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="4c2b1-107">W przypadku złożonych operacji dopasowania do wzorca Użyj <xref:System.Text.RegularExpressions.Regex> klasy.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-107">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c2b1-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="4c2b1-108">Example</span></span>  

 <span data-ttu-id="4c2b1-109">Poniższy przykład wysyła zapytanie do ciągu, aby określić liczbę cyfr, które zawiera.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-109">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="4c2b1-110">Należy pamiętać, że zapytanie jest "ponownie używane" po raz pierwszy.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-110">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="4c2b1-111">Jest to możliwe, ponieważ samo zapytanie nie przechowuje żadnych rzeczywistych wyników.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-111">This is possible because the query itself does not store any actual results.</span></span>  
  
```csharp  
class QueryAString  
{  
    static void Main()  
    {  
        string aString = "ABCDE99F-J74-12-89A";  
  
        // Select only those characters that are numbers  
        IEnumerable<char> stringQuery =  
          from ch in aString  
          where Char.IsDigit(ch)  
          select ch;  
  
        // Execute the query  
        foreach (char c in stringQuery)  
            Console.Write(c + " ");  
  
        // Call the Count method on the existing query.  
        int count = stringQuery.Count();  
        Console.WriteLine("Count = {0}", count);  
  
        // Select all characters before the first '-'  
        IEnumerable<char> stringQuery2 = aString.TakeWhile(c => c != '-');  
  
        // Execute the second query  
        foreach (char c in stringQuery2)  
            Console.Write(c);  
  
        Console.WriteLine(System.Environment.NewLine + "Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
  Output: 9 9 7 4 1 2 8 9  
  Count = 8  
  ABCDE99F  
*/  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4c2b1-112">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="4c2b1-112">Compiling the Code</span></span>  

 <span data-ttu-id="4c2b1-113">Utwórz projekt aplikacji konsolowej w języku C# z `using` dyrektywami dotyczącymi przestrzeni nazw System. LINQ i system.IO.</span><span class="sxs-lookup"><span data-stu-id="4c2b1-113">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c2b1-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4c2b1-114">See also</span></span>

- [<span data-ttu-id="4c2b1-115">LINQ i ciągi (C#)</span><span class="sxs-lookup"><span data-stu-id="4c2b1-115">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="4c2b1-116">Jak połączyć zapytania LINQ z wyrażeniami regularnymi (C#)</span><span class="sxs-lookup"><span data-stu-id="4c2b1-116">How to combine LINQ queries with regular expressions (C#)</span></span>](./how-to-combine-linq-queries-with-regular-expressions.md)
