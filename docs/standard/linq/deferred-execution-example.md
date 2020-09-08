---
title: Przykład wykonania odroczonego — LINQ to XML
description: Dowiedz się, jak odroczone wykonywanie i Ocena z opóźnieniem wpływają na wykonywanie zapytań LINQ to XML.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
ms.openlocfilehash: 59784db895211aecbd263b5ee050734ecd16fa4b
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553472"
---
# <a name="deferred-execution-example-linq-to-xml"></a><span data-ttu-id="89e91-103">Przykład wykonania odroczonego (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="89e91-103">Deferred execution example (LINQ to XML)</span></span>

<span data-ttu-id="89e91-104">W tym artykule pokazano, jak odroczone wykonywanie i Ocena z opóźnieniem wpływają na wykonywanie zapytań LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="89e91-104">This article shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>

## <a name="example-use-the-yield-return-construct-in-an-extension-method-to-defer-execution"></a><span data-ttu-id="89e91-105">Przykład: Użyj `yield return` konstrukcji w metodzie rozszerzenia, aby odroczyć wykonywanie</span><span class="sxs-lookup"><span data-stu-id="89e91-105">Example: Use the `yield return` construct in an extension method to defer execution</span></span>

<span data-ttu-id="89e91-106">Poniższy przykład pokazuje kolejność wykonywania przy użyciu metody rozszerzenia, która korzysta z odroczonego wykonania.</span><span class="sxs-lookup"><span data-stu-id="89e91-106">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="89e91-107">Przykład deklaruje tablicę trzech ciągów.</span><span class="sxs-lookup"><span data-stu-id="89e91-107">The example declares an array of three strings.</span></span> <span data-ttu-id="89e91-108">Następnie wykonuje iterację w kolekcji zwróconej przez `ConvertCollectionToUpperCase` .</span><span class="sxs-lookup"><span data-stu-id="89e91-108">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>

```csharp
public static class LocalExtensions
{
    public static IEnumerable<string>
      ConvertCollectionToUpperCase(this IEnumerable<string> source)
    {
        foreach (string str in source)
        {
            Console.WriteLine("ToUpper: source {0}", str);
            yield return str.ToUpper();
        }
    }
}

class Program
{
    static void Main(string[] args)
    {
        string[] stringArray = { "abc", "def", "ghi" };

        var q = from str in stringArray.ConvertCollectionToUpperCase()
                select str;

        foreach (string str in q)
            Console.WriteLine("Main: str {0}", str);
    }
}
```

```vb
Imports System.Runtime.CompilerServices

Module Module1

    <Extension()>
    Private Iterator Function ConvertCollectionToUpperCase(
    ByVal source As IEnumerable(Of String)) _
    As IEnumerable(Of String)
        For Each str As String In source
            Console.WriteLine("ToUpper: source {0}", str)
            Yield str.ToUpper()
        Next
    End Function

    Sub Main()
        Dim stringArray = New String() {"abc", "def", "ghi"}

        Dim q = From str In stringArray.ConvertCollectionToUpperCase()
                Select str

        For Each Str As String In q
            Console.WriteLine("Main: str {0}", Str)
        Next
    End Sub

End Module
```

<span data-ttu-id="89e91-109">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="89e91-109">This example produces the following output:</span></span>

```output
ToUpper: source abc
Main: str ABC
ToUpper: source def
Main: str DEF
ToUpper: source ghi
Main: str GHI
```

<span data-ttu-id="89e91-110">Należy zauważyć, że podczas iteracji kolekcji zwróconej przez `ConvertCollectionToUpperCase` , każdy element jest pobierany z tablicy ciągów źródłowych i konwertowany na wielkie przed pobraniem następnego elementu z tablicy ciągów źródłowych.</span><span class="sxs-lookup"><span data-stu-id="89e91-110">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>

<span data-ttu-id="89e91-111">Można zobaczyć, że cała tablica ciągów nie jest konwertowana na wielkie przed każdym elementem w zwróconej kolekcji, w `foreach` pętli w `Main` .</span><span class="sxs-lookup"><span data-stu-id="89e91-111">You can see that the entire array of strings isn't converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>

## <a name="see-also"></a><span data-ttu-id="89e91-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="89e91-112">See also</span></span>

- [<span data-ttu-id="89e91-113">Wykonywanie odroczone i Ocena z opóźnieniem</span><span class="sxs-lookup"><span data-stu-id="89e91-113">Deferred execution and lazy evaluation</span></span>](deferred-execution-lazy-evaluation.md)
- [<span data-ttu-id="89e91-114">Samouczek: zapytania łańcuchowe razem (C#)</span><span class="sxs-lookup"><span data-stu-id="89e91-114">Tutorial: Chain queries together (C#)</span></span>](chain-queries-example.md)
