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
# <a name="deferred-execution-example-linq-to-xml"></a>Przykład wykonania odroczonego (LINQ to XML)

W tym artykule pokazano, jak odroczone wykonywanie i Ocena z opóźnieniem wpływają na wykonywanie zapytań LINQ to XML.

## <a name="example-use-the-yield-return-construct-in-an-extension-method-to-defer-execution"></a>Przykład: Użyj `yield return` konstrukcji w metodzie rozszerzenia, aby odroczyć wykonywanie

Poniższy przykład pokazuje kolejność wykonywania przy użyciu metody rozszerzenia, która korzysta z odroczonego wykonania. Przykład deklaruje tablicę trzech ciągów. Następnie wykonuje iterację w kolekcji zwróconej przez `ConvertCollectionToUpperCase` .

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

Ten przykład generuje następujące wyniki:

```output
ToUpper: source abc
Main: str ABC
ToUpper: source def
Main: str DEF
ToUpper: source ghi
Main: str GHI
```

Należy zauważyć, że podczas iteracji kolekcji zwróconej przez `ConvertCollectionToUpperCase` , każdy element jest pobierany z tablicy ciągów źródłowych i konwertowany na wielkie przed pobraniem następnego elementu z tablicy ciągów źródłowych.

Można zobaczyć, że cała tablica ciągów nie jest konwertowana na wielkie przed każdym elementem w zwróconej kolekcji, w `foreach` pętli w `Main` .

## <a name="see-also"></a>Zobacz też

- [Wykonywanie odroczone i Ocena z opóźnieniem](deferred-execution-lazy-evaluation.md)
- [Samouczek: zapytania łańcuchowe razem (C#)](chain-queries-example.md)
