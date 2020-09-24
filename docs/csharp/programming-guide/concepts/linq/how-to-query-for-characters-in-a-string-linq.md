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
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a>Jak wykonać zapytanie o znaki w ciągu (LINQ) (C#)

Ponieważ <xref:System.String> Klasa implementuje <xref:System.Collections.Generic.IEnumerable%601> interfejs ogólny, dowolny ciąg może być badany jako sekwencja znaków. Nie jest to jednak powszechne użycie LINQ. W przypadku złożonych operacji dopasowania do wzorca Użyj <xref:System.Text.RegularExpressions.Regex> klasy.  
  
## <a name="example"></a>Przykład  

 Poniższy przykład wysyła zapytanie do ciągu, aby określić liczbę cyfr, które zawiera. Należy pamiętać, że zapytanie jest "ponownie używane" po raz pierwszy. Jest to możliwe, ponieważ samo zapytanie nie przechowuje żadnych rzeczywistych wyników.  
  
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
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  

 Utwórz projekt aplikacji konsolowej w języku C# z `using` dyrektywami dotyczącymi przestrzeni nazw System. LINQ i system.IO.  
  
## <a name="see-also"></a>Zobacz też

- [LINQ i ciągi (C#)](./linq-and-strings.md)
- [Jak połączyć zapytania LINQ z wyrażeniami regularnymi (C#)](./how-to-combine-linq-queries-with-regular-expressions.md)
