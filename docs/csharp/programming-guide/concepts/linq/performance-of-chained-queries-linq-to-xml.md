---
title: Wydajność zapytań łańcuchowych (LINQ to XML) (C#)
description: Dowiedz się więcej o wydajności zapytań łańcucha. Zapytanie łańcuchowe jest kwerendą, która używa innego zapytania jako źródła.
ms.date: 07/20/2015
ms.assetid: b2f1d715-8946-4dc0-8d56-fb3d1bba54a6
ms.openlocfilehash: 1e9173e85845dd085f4d7bf6deec7eb498acd7f3
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302857"
---
# <a name="performance-of-chained-queries-linq-to-xml-c"></a><span data-ttu-id="0375a-104">Wydajność zapytań łańcuchowych (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0375a-104">Performance of Chained Queries (LINQ to XML) (C#)</span></span>

<span data-ttu-id="0375a-105">Jedną z najważniejszych zalet LINQ (i LINQ to XML) jest to, że kwerendy łańcuchowe mogą wykonywać, a także pojedyncze, bardziej skomplikowane zapytania.</span><span class="sxs-lookup"><span data-stu-id="0375a-105">One of the most important benefits of LINQ (and LINQ to XML) is that chained queries can perform as well as a single larger, more complicated query.</span></span>

<span data-ttu-id="0375a-106">Zapytanie łańcuchowe jest kwerendą, która używa innego zapytania jako źródła.</span><span class="sxs-lookup"><span data-stu-id="0375a-106">A chained query is a query that uses another query as its source.</span></span> <span data-ttu-id="0375a-107">Na przykład, w poniższym prostym kodzie, `query2` ma `query1` jako Źródło:</span><span class="sxs-lookup"><span data-stu-id="0375a-107">For example, in the following simple code, `query2` has `query1` as its source:</span></span>

```csharp
XElement root = new XElement("Root",
    new XElement("Child", 1),
    new XElement("Child", 2),
    new XElement("Child", 3),
    new XElement("Child", 4)
);

var query1 = from x in root.Elements("Child")
             where (int)x >= 3
             select x;

var query2 = from e in query1
             where (int)e % 2 == 0
             select e;

foreach (var i in query2)
    Console.WriteLine("{0}", (int)i);
```

<span data-ttu-id="0375a-108">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="0375a-108">This example produces the following output:</span></span>

```output
4
```

<span data-ttu-id="0375a-109">To zapytanie łańcuchowe zapewnia ten sam profil wydajności co iteracja w połączonej liście.</span><span class="sxs-lookup"><span data-stu-id="0375a-109">This chained query provides the same performance profile as iterating through a linked list.</span></span>

- <span data-ttu-id="0375a-110"><xref:System.Xml.Linq.XContainer.Elements%2A>Oś ma zasadniczo taką samą wydajność jak iteracja w połączonej liście.</span><span class="sxs-lookup"><span data-stu-id="0375a-110">The <xref:System.Xml.Linq.XContainer.Elements%2A> axis has essentially the same performance as iterating through a linked list.</span></span> <span data-ttu-id="0375a-111"><xref:System.Xml.Linq.XContainer.Elements%2A>jest zaimplementowany jako iterator z odroczonym wykonaniem.</span><span class="sxs-lookup"><span data-stu-id="0375a-111"><xref:System.Xml.Linq.XContainer.Elements%2A> is implemented as an iterator with deferred execution.</span></span> <span data-ttu-id="0375a-112">Oznacza to, że wykonuje kilka zadań oprócz iteracji przez połączoną listę, na przykład przydzielanie obiektu iteratora i śledzenie stanu wykonywania.</span><span class="sxs-lookup"><span data-stu-id="0375a-112">This means that it does some work in addition to iterating through the linked list, such as allocating the iterator object and keeping track of execution state.</span></span> <span data-ttu-id="0375a-113">Ta czynność może zostać podzielona na dwie kategorie: pracy, która jest wykonywana w chwili, gdy iterator jest skonfigurowany, i pracy, która jest wykonywana podczas każdej iteracji.</span><span class="sxs-lookup"><span data-stu-id="0375a-113">This work can be divided into two categories: the work that is done at the time the iterator is set up, and the work that is done during each iteration.</span></span> <span data-ttu-id="0375a-114">Konfiguracja pracy jest małą, stałą ilością pracy i pracy wykonywanej podczas każdej iteracji jest proporcjonalna do liczby elementów w kolekcji źródłowej.</span><span class="sxs-lookup"><span data-stu-id="0375a-114">The setup work is a small, fixed amount of work and the work done during each iteration is proportional to the number of items in the source collection.</span></span>

- <span data-ttu-id="0375a-115">W programie `query1` `where` klauzula powoduje wywołanie <xref:System.Linq.Enumerable.Where%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="0375a-115">In `query1`, the `where` clause causes the query to call the <xref:System.Linq.Enumerable.Where%2A> method.</span></span> <span data-ttu-id="0375a-116">Ta metoda jest również zaimplementowana jako iterator.</span><span class="sxs-lookup"><span data-stu-id="0375a-116">This method is also implemented as an iterator.</span></span> <span data-ttu-id="0375a-117">Konfiguracja zadań składa się z tworzenia wystąpienia delegata, który będzie odwoływać się do wyrażenia lambda oraz normalnej konfiguracji iteratora.</span><span class="sxs-lookup"><span data-stu-id="0375a-117">The setup work consists of instantiating the delegate that will reference the lambda expression, plus the normal setup for an iterator.</span></span> <span data-ttu-id="0375a-118">Dla każdej iteracji delegat jest wywoływany, aby wykonać predykat.</span><span class="sxs-lookup"><span data-stu-id="0375a-118">With each iteration, the delegate is called to execute the predicate.</span></span> <span data-ttu-id="0375a-119">Konfiguracja pracy i pracy wykonanej podczas każdej iteracji jest podobna do wykonanej pracy podczas iteracji na osi.</span><span class="sxs-lookup"><span data-stu-id="0375a-119">The setup work and the work done during each iteration is the similar to the work done while iterating through the axis.</span></span>

- <span data-ttu-id="0375a-120">W programie `query1` klauzula SELECT powoduje, że zapytanie wywołuje <xref:System.Linq.Enumerable.Select%2A> metodę.</span><span class="sxs-lookup"><span data-stu-id="0375a-120">In `query1`, the select clause causes the query to call the <xref:System.Linq.Enumerable.Select%2A> method.</span></span> <span data-ttu-id="0375a-121">Ta metoda ma ten sam profil wydajności co <xref:System.Linq.Enumerable.Where%2A> Metoda.</span><span class="sxs-lookup"><span data-stu-id="0375a-121">This method has the same performance profile as the <xref:System.Linq.Enumerable.Where%2A> method.</span></span>

- <span data-ttu-id="0375a-122">W programie `query2` obie `where` klauzule i `select` klauzula mają taki sam profil wydajności jak w `query1` .</span><span class="sxs-lookup"><span data-stu-id="0375a-122">In `query2`, both the `where` clause and the `select` clause have the same performance profile as in `query1`.</span></span>

<span data-ttu-id="0375a-123">Iteracja w programie `query2` jest w związku z tym bezpośrednio proporcjonalna do liczby elementów w źródle pierwszego zapytania, czyli czasu liniowego.</span><span class="sxs-lookup"><span data-stu-id="0375a-123">The iteration through `query2` is therefore directly proportional to the number of items in the source of the first query, in other words, linear time.</span></span> <span data-ttu-id="0375a-124">Odpowiadający przykład Visual Basic będzie miał ten sam profil wydajności.</span><span class="sxs-lookup"><span data-stu-id="0375a-124">A corresponding Visual Basic example would have the same performance profile.</span></span>

<span data-ttu-id="0375a-125">Aby uzyskać więcej informacji na temat iteratorów, zobacz [Yield](../../../language-reference/keywords/yield.md).</span><span class="sxs-lookup"><span data-stu-id="0375a-125">For more information on iterators, see [yield](../../../language-reference/keywords/yield.md).</span></span>

<span data-ttu-id="0375a-126">Aby zapoznać się z bardziej szczegółowym samouczkiem dotyczącym łączenia zapytań, zobacz [Samouczek: Łączenie łańcuchowe zapytań](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0375a-126">For a more detailed tutorial on chaining queries together, see [Tutorial: Chaining Queries Together](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>
