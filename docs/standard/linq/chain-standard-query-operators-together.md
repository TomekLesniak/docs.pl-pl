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
# <a name="chain-standard-query-operators-together-c-linq-to-xml"></a><span data-ttu-id="6b02f-103">Standardowe operatory zapytań łańcucha (C#) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="6b02f-103">Chain standard query operators together (C#) (LINQ to XML)</span></span>

<span data-ttu-id="6b02f-104">Standardowe operatory zapytań można łączyć ze sobą.</span><span class="sxs-lookup"><span data-stu-id="6b02f-104">The standard query operators can be chained together.</span></span> <span data-ttu-id="6b02f-105">Na przykład można interject <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> operator (wywoływany przez `where` klauzulę) i działa w oczekiwany sposób, czyli nie są w nim wykonywane żadne pośrednie wyniki.</span><span class="sxs-lookup"><span data-stu-id="6b02f-105">For example, you can interject the <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> operator (invoked by the `where` clause), and it operates in a lazy fashion; that is, no intermediate results are materialized by it.</span></span>

## <a name="example-interject-a-where-clause"></a><span data-ttu-id="6b02f-106">Przykład: interject klauzuli WHERE</span><span class="sxs-lookup"><span data-stu-id="6b02f-106">Example: Interject a where clause</span></span>

<span data-ttu-id="6b02f-107">W tym przykładzie <xref:System.Linq.Enumerable.Where%2A> Metoda jest wywoływana przed wywołaniem `ConvertCollectionToUpperCase` .</span><span class="sxs-lookup"><span data-stu-id="6b02f-107">In this example, the <xref:System.Linq.Enumerable.Where%2A> method is called before calling `ConvertCollectionToUpperCase`.</span></span> <span data-ttu-id="6b02f-108"><xref:System.Linq.Enumerable.Where%2A>Metoda działa w prawie dokładnie taki sam sposób, jak metody opóźnione używane w poprzednich przykładach w tym samouczku `ConvertCollectionToUpperCase` i `AppendString` .</span><span class="sxs-lookup"><span data-stu-id="6b02f-108">The <xref:System.Linq.Enumerable.Where%2A> method operates in almost exactly the same way as the lazy methods used in previous examples in this tutorial, `ConvertCollectionToUpperCase` and `AppendString`.</span></span>

<span data-ttu-id="6b02f-109">Jedną z różnic jest to, że w tym przypadku <xref:System.Linq.Enumerable.Where%2A> Metoda iteruje za pomocą kolekcji źródłowej, określa, że pierwszy element nie przekazuje predykatu, a następnie pobiera następny element, który jest przekazywany.</span><span class="sxs-lookup"><span data-stu-id="6b02f-109">One difference is that in this case, the <xref:System.Linq.Enumerable.Where%2A> method iterates through its source collection, determines that the first item doesn't pass the predicate, and then gets the next item, which does pass.</span></span> <span data-ttu-id="6b02f-110">Następnie zwraca drugi element.</span><span class="sxs-lookup"><span data-stu-id="6b02f-110">It then yields the second item.</span></span>

<span data-ttu-id="6b02f-111">Jednak podstawowe pomysły są takie same: Kolekcje pośrednie nie są materiałowe, chyba że muszą być.</span><span class="sxs-lookup"><span data-stu-id="6b02f-111">However, the basic idea is the same: intermediate collections aren't materialized unless they have to be.</span></span>

<span data-ttu-id="6b02f-112">Gdy wyrażenia zapytania są używane, są konwertowane na wywołania do standardowych operatorów zapytań i obowiązują te same zasady.</span><span class="sxs-lookup"><span data-stu-id="6b02f-112">When query expressions are used, they're converted to calls to the standard query operators, and the same principles apply.</span></span>

<span data-ttu-id="6b02f-113">Wszystkie przykłady w tej sekcji, które wykonują zapytania o dokumenty w programie Office Open XML, używają tej samej zasady.</span><span class="sxs-lookup"><span data-stu-id="6b02f-113">All of the examples in this section that are querying Office Open XML documents use the same principle.</span></span> <span data-ttu-id="6b02f-114">Odroczone wykonywanie i Ocena z opóźnieniem to niektóre podstawowe koncepcje, które należy zrozumieć, aby używać LINQ i LINQ to XML, efektywnie.</span><span class="sxs-lookup"><span data-stu-id="6b02f-114">Deferred execution and lazy evaluation are some of the fundamental concepts that you must understand to use LINQ, and LINQ to XML, effectively.</span></span>

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

<span data-ttu-id="6b02f-115">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="6b02f-115">This example produces the following output:</span></span>

```output
ToUpper: source >abc<
ToUpper: source >def<
AppendString: source >DEF<
Main: str >DEF!!!<

ToUpper: source >ghi<
AppendString: source >GHI<
Main: str >GHI!!!<
```

<span data-ttu-id="6b02f-116">Jest to ostatni artykuł w [samouczku: Tworzenie łańcucha kwerend razem (C#)](chain-queries-example.md) samouczek.</span><span class="sxs-lookup"><span data-stu-id="6b02f-116">This is the final article in the [Tutorial: Chaining Queries Together (C#)](chain-queries-example.md) tutorial.</span></span>
