---
title: Standardowe operatory zapytań łańcucha (C#) — LINQ to XML
description: Dowiedz się, jak łączyć operatory zapytań ze sobą.
ms.date: 07/20/2015
dev_langs:
- csharp
ms.assetid: 66f2b0a9-2c23-4735-988e-bbc9dfb55c7b
ms.openlocfilehash: ed3ca44c853ebbeee690cb31232a13e35b383d1b
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552906"
---
# <a name="chain-standard-query-operators-together-c-linq-to-xml"></a>Standardowe operatory zapytań łańcucha (C#) (LINQ to XML)

Standardowe operatory zapytań można łączyć ze sobą. Na przykład można interject <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> operator (wywoływany przez `where` klauzulę) i działa w oczekiwany sposób, czyli nie są w nim wykonywane żadne pośrednie wyniki.

## <a name="example-interject-a-where-clause"></a>Przykład: interject klauzuli WHERE

W tym przykładzie <xref:System.Linq.Enumerable.Where%2A> Metoda jest wywoływana przed wywołaniem `ConvertCollectionToUpperCase` . <xref:System.Linq.Enumerable.Where%2A>Metoda działa w prawie dokładnie taki sam sposób, jak metody opóźnione używane w poprzednich przykładach w tym samouczku `ConvertCollectionToUpperCase` i `AppendString` .

Jedną z różnic jest to, że w tym przypadku <xref:System.Linq.Enumerable.Where%2A> Metoda iteruje za pomocą kolekcji źródłowej, określa, że pierwszy element nie przekazuje predykatu, a następnie pobiera następny element, który jest przekazywany. Następnie zwraca drugi element.

Jednak podstawowe pomysły są takie same: Kolekcje pośrednie nie są materiałowe, chyba że muszą być.

Gdy wyrażenia zapytania są używane, są konwertowane na wywołania do standardowych operatorów zapytań i obowiązują te same zasady.

Wszystkie przykłady w tej sekcji, które wykonują zapytania o dokumenty w programie Office Open XML, używają tej samej zasady. Odroczone wykonywanie i Ocena z opóźnieniem to niektóre podstawowe koncepcje, które należy zrozumieć, aby używać LINQ i LINQ to XML, efektywnie.

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
            where s.CompareTo("D") >= 0
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
ToUpper: source >def<
AppendString: source >DEF<
Main: str >DEF!!!<

ToUpper: source >ghi<
AppendString: source >GHI<
Main: str >GHI!!!<
```

Jest to ostatni artykuł w [samouczku: Tworzenie łańcucha kwerend razem (C#)](chain-queries-example.md) samouczek.
