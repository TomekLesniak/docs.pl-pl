---
title: Przykład zapytań łańcuchowych (C#) — LINQ to XML
description: Dowiedz się, co się dzieje w przypadku łączenia dwóch zapytań, które używają odroczonego wykonania i oceny z opóźnieniem.
ms.date: 07/20/2015
ms.assetid: abbca162-d95e-43af-b92c-e46e6aa2540e
ms.openlocfilehash: c0bbab9061b98eda15523f8a8e64e997bde8b307
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553491"
---
# <a name="chain-queries-example-c-linq-to-xml"></a>Przykład zapytań łańcucha (C#) (LINQ to XML)

Ten przykład jest oparty na przykładzie w [odroczonym przykładzie wykonywania](deferred-execution-example.md) i pokazuje, co się dzieje w przypadku łączenia dwóch zapytań, które używają odroczonego wykonania i oceny z opóźnieniem.

## <a name="example-add-a-second-extension-method-that-uses-yield-return-to-defer-execution"></a>Przykład: Dodaj drugą metodę rozszerzenia używaną `yield return` w celu odroczenia wykonania

W tym przykładzie wprowadzono inną metodę rozszerzenia, `AppendString` która dołącza określony ciąg do każdego ciągu w kolekcji źródłowej, a następnie zwraca zmieniony ciąg.

```csharp
public static class LocalExtensions
{
    public static IEnumerable<string>
      ConvertCollectionToUpperCase(this IEnumerable<string> source)
    {
        foreach (string str in source)
        {
            Console.WriteLine("ToUpper: source >{0}<", str);
            yield return str.ToUpper();
        }
    }

    public static IEnumerable<string>
      AppendString(this IEnumerable<string> source, string stringToAppend)
    {
        foreach (string str in source)
        {
            Console.WriteLine("AppendString: source >{0}<", str);
            yield return str + stringToAppend;
        }
    }
}

class Program
{
    static void Main(string[] args)
    {
        string[] stringArray = { "abc", "def", "ghi" };

        IEnumerable<string> q1 =
            from s in stringArray.ConvertCollectionToUpperCase()
            select s;

        IEnumerable<string> q2 =
            from s in q1.AppendString("!!!")
            select s;

        foreach (string str in q2)
        {
            Console.WriteLine("Main: str >{0}<", str);
            Console.WriteLine();
        }
    }
}
```

 Ten przykład generuje następujące wyniki:

```output
ToUpper: source >abc<
AppendString: source >ABC<
Main: str >ABC!!!<

ToUpper: source >def<
AppendString: source >DEF<
Main: str >DEF!!!<

ToUpper: source >ghi<
AppendString: source >GHI<
Main: str >GHI!!!<
```

W tym przykładzie można zobaczyć, że każda metoda rozszerzająca działa pojedynczo dla każdego elementu w kolekcji źródłowej.

Co powinno być jasne z tego przykładu, chociaż istnieją łańcuchowe zapytania, które przesyłają kolekcje, a żadne kolekcje pośrednie nie są przeznaczone do materiałów. Zamiast tego każdy element jest przesyłany z jednej metody opóźnionej do następnej. Powoduje to znacznie mniejszą ilość pamięci niż podejście, które najpierw przyjmuje jedną tablicę ciągów, a następnie tworzy drugą tablicę ciągów, które zostały przekonwertowane na wielkie litery, i na koniec tworzy trzecią tablicę ciągów, w których każdy ciąg ma do niej dołączony wykrzyknik.

W następnym artykule z tego samouczka przedstawiono materializację pośredni:

- [Pośredni materializację (C#)](intermediate-materialization.md)

## <a name="see-also"></a>Zobacz też

- [Wykonywanie odroczone i Ocena z opóźnieniem](deferred-execution-lazy-evaluation.md)
