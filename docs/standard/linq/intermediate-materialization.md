---
title: Pośredni materializację (C#)
description: Dowiedz się, jak używać niektórych standardowych operatorów zapytań, które mogą spowodować materializację kolekcji w zapytaniu, i radykalnie zmienić profil pamięci i wydajności aplikacji.
ms.date: 07/20/2015
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
ms.openlocfilehash: 8dca4bb29886973762351049d06bcf5d3ba352db
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552963"
---
# <a name="intermediate-materialization-c"></a><span data-ttu-id="05273-103">Pośredni materializację (C#)</span><span class="sxs-lookup"><span data-stu-id="05273-103">Intermediate materialization (C#)</span></span>

<span data-ttu-id="05273-104">Jeśli nie widzisz ostrożności, możesz w niektórych sytuacjach radykalnie zmienić profil pamięci i wydajności aplikacji, powodując przedwcześnie materializację kolekcji w zapytaniach.</span><span class="sxs-lookup"><span data-stu-id="05273-104">If you're not careful you can, in some situations, drastically alter the memory and performance profile of your application by causing premature materialization of collections in your queries.</span></span> <span data-ttu-id="05273-105">Niektóre standardowe operatory zapytań powodują materializację kolekcji źródłowej przed uzyskaniem pojedynczego elementu.</span><span class="sxs-lookup"><span data-stu-id="05273-105">Some standard query operators cause materialization of their source collection before yielding a single element.</span></span> <span data-ttu-id="05273-106">Na przykład program <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> najpierw wykonuje iterację w całej kolekcji źródłowej, sortuje wszystkie elementy, a następnie zwraca pierwszy element.</span><span class="sxs-lookup"><span data-stu-id="05273-106">For example, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> first iterates through its entire source collection, then sorts all items, and then finally yields the first item.</span></span> <span data-ttu-id="05273-107">Oznacza to, że jest kosztowne uzyskanie pierwszego elementu kolekcji uporządkowanej; Każdy element nie jest kosztowny.</span><span class="sxs-lookup"><span data-stu-id="05273-107">This means that it's expensive to get the first item of an ordered collection; each item thereafter isn't expensive.</span></span> <span data-ttu-id="05273-108">Jest to zrozumiałe: byłoby niemożliwe dla tego operatora zapytań.</span><span class="sxs-lookup"><span data-stu-id="05273-108">This makes sense: It would be impossible for that query operator to do otherwise.</span></span>

## <a name="example-add-a-method-that-calls-tolist-causing-materialization"></a><span data-ttu-id="05273-109">Przykład: Dodaj metodę, która wywołuje `ToList` , powodując materializację</span><span class="sxs-lookup"><span data-stu-id="05273-109">Example: Add a method that calls `ToList`, causing materialization</span></span>

<span data-ttu-id="05273-110">Ten przykład zmienia przykład w przykładzie [kwerend łańcucha (C#)](chain-queries-example.md): `AppendString` Metoda jest zmieniana na wywołanie <xref:System.Linq.Enumerable.ToList%2A> przed iteracją, co powoduje materializację.</span><span class="sxs-lookup"><span data-stu-id="05273-110">This example alters the example in [Chain queries example (C#)](chain-queries-example.md): the `AppendString` method is changed to call <xref:System.Linq.Enumerable.ToList%2A> before iterating through the source, which causes materialization.</span></span>

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
        // the following statement materializes the source collection in a List<T>
        // before iterating through it
        foreach (string str in source.ToList())
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

 <span data-ttu-id="05273-111">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="05273-111">This example produces the following output:</span></span>

```output
ToUpper: source >abc<
ToUpper: source >def<
ToUpper: source >ghi<
AppendString: source >ABC<
Main: str >ABC!!!<

AppendString: source >DEF<
Main: str >DEF!!!<

AppendString: source >GHI<
Main: str >GHI!!!<
```

<span data-ttu-id="05273-112">W tym przykładzie można zobaczyć, że wywołanie <xref:System.Linq.Enumerable.ToList%2A> powoduje `AppendString` Wyliczenie całego źródła przed uzyskaniem pierwszego elementu.</span><span class="sxs-lookup"><span data-stu-id="05273-112">In this example, you can see that the call to <xref:System.Linq.Enumerable.ToList%2A> causes `AppendString` to enumerate its entire source before yielding the first item.</span></span> <span data-ttu-id="05273-113">Jeśli źródłem była duża tablica, znacznie zmienia profil pamięci aplikacji.</span><span class="sxs-lookup"><span data-stu-id="05273-113">If the source were a large array, this would significantly alter the memory profile of the application.</span></span>

<span data-ttu-id="05273-114">Standardowe operatory zapytań można również łączyć w łańcuchy, jak pokazano w końcowym artykule w tym samouczku:</span><span class="sxs-lookup"><span data-stu-id="05273-114">Standard query operators can also be chained together as shown in the final article in this tutorial:</span></span>

- [<span data-ttu-id="05273-115">Standardowe operatory zapytań łańcucha (C#)</span><span class="sxs-lookup"><span data-stu-id="05273-115">Chain standard query operators together (C#)</span></span>](chain-standard-query-operators-together.md)

## <a name="see-also"></a><span data-ttu-id="05273-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="05273-116">See also</span></span>

- [<span data-ttu-id="05273-117">Wykonywanie odroczone i Ocena z opóźnieniem</span><span class="sxs-lookup"><span data-stu-id="05273-117">Deferred execution and lazy evaluation</span></span>](deferred-execution-lazy-evaluation.md)
