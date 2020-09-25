---
title: Sortowanie lub filtrowanie danych tekstowych według dowolnego wyrazu lub pola (LINQ) (C#)
description: Dowiedz się, jak sortować lub filtrować dane tekstowe według dowolnego wyrazu lub pola. Zobacz przykład sortowania wierszy tekstu strukturalnego według dowolnego pola w wierszu.
ms.date: 07/20/2015
ms.assetid: 7c04d42f-4a78-42c8-9ec8-57ef18fe13a9
ms.openlocfilehash: 05858cc787d3916b204910df10d3291796cebc02
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203946"
---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-c"></a><span data-ttu-id="00754-104">Sortowanie lub filtrowanie danych tekstowych według dowolnego wyrazu lub pola (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="00754-104">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>

<span data-ttu-id="00754-105">Poniższy przykład pokazuje, jak sortować wiersze tekstu strukturalnego, takie jak wartości rozdzielane przecinkami, według dowolnego pola w wierszu.</span><span class="sxs-lookup"><span data-stu-id="00754-105">The following example shows how to sort lines of structured text, such as comma-separated values, by any field in the line.</span></span> <span data-ttu-id="00754-106">Pole może być określane dynamicznie w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="00754-106">The field may be dynamically specified at runtime.</span></span> <span data-ttu-id="00754-107">Załóżmy, że pola w scores.csv reprezentują numer IDENTYFIKACYJNy studenta, a następnie serię czterech wyników testu.</span><span class="sxs-lookup"><span data-stu-id="00754-107">Assume that the fields in scores.csv represent a student's ID number, followed by a series of four test scores.</span></span>  
  
### <a name="to-create-a-file-that-contains-data"></a><span data-ttu-id="00754-108">Aby utworzyć plik zawierający dane</span><span class="sxs-lookup"><span data-stu-id="00754-108">To create a file that contains data</span></span>  
  
1. <span data-ttu-id="00754-109">Skopiuj scores.csv dane z tematu, [jak dołączyć zawartość z niepodobnych plików (LINQ) (C#](./how-to-join-content-from-dissimilar-files-linq.md) ) i zapisać je w folderze rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="00754-109">Copy the scores.csv data from the topic [How to join content from dissimilar files (LINQ) (C#)](./how-to-join-content-from-dissimilar-files-linq.md) and save it to your solution folder.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00754-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="00754-110">Example</span></span>  
  
```csharp  
public class SortLines  
{  
    static void Main()  
    {  
        // Create an IEnumerable data source  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Change this to any value from 0 to 4.  
        int sortField = 1;  
  
        Console.WriteLine("Sorted highest to lowest by field [{0}]:", sortField);  
  
        // Demonstrates how to return query from a method.  
        // The query is executed here.  
        foreach (string str in RunQuery(scores, sortField))  
        {  
            Console.WriteLine(str);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // Returns the query variable, not query results!  
    static IEnumerable<string> RunQuery(IEnumerable<string> source, int num)  
    {  
        // Split the string and sort on field[num]  
        var scoreQuery = from line in source  
                         let fields = line.Split(',')  
                         orderby fields[num] descending  
                         select line;  
  
        return scoreQuery;  
    }  
}  
/* Output (if sortField == 1):  
   Sorted highest to lowest by field [1]:  
    116, 99, 86, 90, 94  
    120, 99, 82, 81, 79  
    111, 97, 92, 81, 60  
    114, 97, 89, 85, 82  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    113, 88, 94, 65, 91  
    112, 75, 84, 91, 39  
    119, 68, 79, 88, 92  
    115, 35, 72, 91, 70  
 */  
```  
  
 <span data-ttu-id="00754-111">W tym przykładzie pokazano również, jak zwrócić zmienną zapytania z metody.</span><span class="sxs-lookup"><span data-stu-id="00754-111">This example also demonstrates how to return a query variable from a method.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="00754-112">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="00754-112">Compiling the Code</span></span>  

<span data-ttu-id="00754-113">Utwórz projekt aplikacji konsolowej w języku C# z `using` dyrektywami dotyczącymi przestrzeni nazw System. LINQ i system.IO.</span><span class="sxs-lookup"><span data-stu-id="00754-113">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="00754-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="00754-114">See also</span></span>

- [<span data-ttu-id="00754-115">LINQ i ciągi (C#)</span><span class="sxs-lookup"><span data-stu-id="00754-115">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
