---
title: Zapisywanie zapytań LINQ w C#
description: Dowiedz się, jak pisać zapytania LINQ w języku C#.
ms.date: 12/01/2016
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
ms.openlocfilehash: bd7da81f2873c6a25570cab32fafecc66fd98be4
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063448"
---
# <a name="write-linq-queries-in-c"></a><span data-ttu-id="465c6-103">Zapisz zapytania LINQ w języku C\#</span><span class="sxs-lookup"><span data-stu-id="465c6-103">Write LINQ queries in C\#</span></span>

<span data-ttu-id="465c6-104">W tym artykule przedstawiono trzy sposoby pisania zapytania LINQ w języku C#:</span><span class="sxs-lookup"><span data-stu-id="465c6-104">This article shows the three ways in which you can write a LINQ query in C#:</span></span>

1. <span data-ttu-id="465c6-105">Użyj składni zapytania.</span><span class="sxs-lookup"><span data-stu-id="465c6-105">Use query syntax.</span></span>

2. <span data-ttu-id="465c6-106">Użyj składni metody.</span><span class="sxs-lookup"><span data-stu-id="465c6-106">Use method syntax.</span></span>

3. <span data-ttu-id="465c6-107">Użyj kombinacji składni zapytania i składni metody.</span><span class="sxs-lookup"><span data-stu-id="465c6-107">Use a combination of query syntax and method syntax.</span></span>

<span data-ttu-id="465c6-108">W poniższych przykładach przedstawiono niektóre proste zapytania LINQ przy użyciu każdego z wymienionych wcześniej metod.</span><span class="sxs-lookup"><span data-stu-id="465c6-108">The following examples demonstrate some simple LINQ queries by using each approach listed previously.</span></span> <span data-ttu-id="465c6-109">Ogólnie rzecz biorąc, reguła jest używana (1) zawsze, gdy jest to możliwe, i w razie potrzeby używa (2) i (3).</span><span class="sxs-lookup"><span data-stu-id="465c6-109">In general, the rule is to use (1) whenever possible, and use (2) and (3) whenever necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="465c6-110">Te zapytania działają w prostych kolekcjach w pamięci; Jednak podstawowa składnia jest taka sama jak używana w LINQ to Entities i LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="465c6-110">These queries operate on simple in-memory collections; however, the basic syntax is identical to that used in LINQ to Entities and LINQ to XML.</span></span>

## <a name="example---query-syntax"></a><span data-ttu-id="465c6-111">Przykład — Składnia zapytania</span><span class="sxs-lookup"><span data-stu-id="465c6-111">Example - Query syntax</span></span>

<span data-ttu-id="465c6-112">Zalecanym sposobem zapisu większości zapytań jest użycie *składni zapytań* w celu utworzenia *wyrażeń zapytania*.</span><span class="sxs-lookup"><span data-stu-id="465c6-112">The recommended way to write most queries is to use *query syntax* to create *query expressions*.</span></span> <span data-ttu-id="465c6-113">Poniższy przykład pokazuje trzy wyrażenia zapytania.</span><span class="sxs-lookup"><span data-stu-id="465c6-113">The following example shows three query expressions.</span></span> <span data-ttu-id="465c6-114">Pierwsze wyrażenie zapytania pokazuje, jak filtrować lub ograniczać wyniki, stosując warunki z `where` klauzulą.</span><span class="sxs-lookup"><span data-stu-id="465c6-114">The first query expression demonstrates how to filter or restrict results by applying conditions with a `where` clause.</span></span> <span data-ttu-id="465c6-115">Zwraca wszystkie elementy w sekwencji źródłowej, których wartości są większe niż 7 lub mniejsze niż 3.</span><span class="sxs-lookup"><span data-stu-id="465c6-115">It returns all elements in the source sequence whose values are greater than 7 or less than 3.</span></span> <span data-ttu-id="465c6-116">Drugie wyrażenie ilustruje sposób uporządkowania zwracanych wyników.</span><span class="sxs-lookup"><span data-stu-id="465c6-116">The second expression demonstrates how to order the returned results.</span></span> <span data-ttu-id="465c6-117">Trzecie wyrażenie ilustruje sposób grupowania wyników według klucza.</span><span class="sxs-lookup"><span data-stu-id="465c6-117">The third expression demonstrates how to group results according to a key.</span></span> <span data-ttu-id="465c6-118">To zapytanie zwraca dwie grupy w oparciu o pierwszą literę wyrazu.</span><span class="sxs-lookup"><span data-stu-id="465c6-118">This query returns two groups based on the first letter of the word.</span></span>

[!code-csharp[csProgGuideLINQ#5](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]

<span data-ttu-id="465c6-119">Należy pamiętać, że typ zapytań to <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="465c6-119">Note that the type of the queries is <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="465c6-120">Wszystkie te zapytania można napisać przy użyciu `var` , jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="465c6-120">All of these queries could be written using `var` as shown in the following example:</span></span>

`var query = from num in numbers...`

<span data-ttu-id="465c6-121">W każdym poprzednim przykładzie zapytania nie są wykonywane, dopóki nie zostanie wykonana iteracja zmiennej zapytania w `foreach` instrukcji lub innej instrukcji.</span><span class="sxs-lookup"><span data-stu-id="465c6-121">In each previous example, the queries do not actually execute until you iterate over the query variable in a `foreach` statement or other statement.</span></span> <span data-ttu-id="465c6-122">Aby uzyskać więcej informacji, zobacz [wprowadzenie do zapytań LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="465c6-122">For more information, see [Introduction to LINQ Queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

## <a name="example---method-syntax"></a><span data-ttu-id="465c6-123">Przykład — składnia metody</span><span class="sxs-lookup"><span data-stu-id="465c6-123">Example - Method syntax</span></span>

<span data-ttu-id="465c6-124">Niektóre operacje zapytań muszą być wyrażone jako wywołanie metody.</span><span class="sxs-lookup"><span data-stu-id="465c6-124">Some query operations must be expressed as a method call.</span></span> <span data-ttu-id="465c6-125">Najbardziej powszechnymi metodami są te, które zwracają pojedyncze wartości liczbowe, takie jak,,, <xref:System.Linq.Enumerable.Sum%2A> <xref:System.Linq.Enumerable.Max%2A> <xref:System.Linq.Enumerable.Min%2A> <xref:System.Linq.Enumerable.Average%2A> i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="465c6-125">The most common such methods are those that return singleton numeric values, such as <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A>, and so on.</span></span> <span data-ttu-id="465c6-126">Te metody muszą zawsze być wywoływane jako ostatnie w dowolnych zapytaniach, ponieważ reprezentują tylko jedną wartość i nie mogą służyć jako źródło dodatkowej operacji zapytania.</span><span class="sxs-lookup"><span data-stu-id="465c6-126">These methods must always be called last in any query because they represent only a single value and cannot serve as the source for an additional query operation.</span></span> <span data-ttu-id="465c6-127">W poniższym przykładzie pokazano wywołanie metody w wyrażeniu zapytania:</span><span class="sxs-lookup"><span data-stu-id="465c6-127">The following example shows a method call in a query expression:</span></span>

[!code-csharp[csProgGuideLINQ#6](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]

<span data-ttu-id="465c6-128">Jeśli metoda zawiera parametry akcji lub Func, są one dostępne w formie wyrażenia [lambda](../language-reference/operators/lambda-expressions.md) , jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="465c6-128">If the method has Action or Func parameters, these are provided in the form of a [lambda](../language-reference/operators/lambda-expressions.md) expression, as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#7](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]

<span data-ttu-id="465c6-129">W poprzednich zapytaniach tylko #4 zapytań są wykonywane.</span><span class="sxs-lookup"><span data-stu-id="465c6-129">In the previous queries, only Query #4 executes immediately.</span></span> <span data-ttu-id="465c6-130">Dzieje się tak, ponieważ zwraca pojedynczą wartość, a nie ogólną <xref:System.Collections.Generic.IEnumerable%601> kolekcję.</span><span class="sxs-lookup"><span data-stu-id="465c6-130">This is because it returns a single value, and not a generic <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="465c6-131">Aby `foreach` można było obliczyć jego wartość, należy użyć samej metody.</span><span class="sxs-lookup"><span data-stu-id="465c6-131">The method itself has to use `foreach` in order to compute its value.</span></span>

<span data-ttu-id="465c6-132">Wszystkie poprzednie zapytania można napisać przy użyciu niejawnego wpisywania z [var](../language-reference/keywords/var.md), jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="465c6-132">Each of the previous queries can be written by using implicit typing with [var](../language-reference/keywords/var.md), as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#8](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]

## <a name="example---mixed-query-and-method-syntax"></a><span data-ttu-id="465c6-133">Przykład — mieszane składnie zapytań i metod</span><span class="sxs-lookup"><span data-stu-id="465c6-133">Example - Mixed query and method syntax</span></span>

<span data-ttu-id="465c6-134">Ten przykład pokazuje, jak używać składni metody na wynikach klauzuli zapytania.</span><span class="sxs-lookup"><span data-stu-id="465c6-134">This example shows how to use method syntax on the results of a query clause.</span></span> <span data-ttu-id="465c6-135">Po prostu umieść wyrażenie zapytania w nawiasach, a następnie Zastosuj operator kropki i Wywołaj metodę.</span><span class="sxs-lookup"><span data-stu-id="465c6-135">Just enclose the query expression in parentheses, and then apply the dot operator and call the method.</span></span> <span data-ttu-id="465c6-136">W poniższym przykładzie zapytanie #7 zwraca liczbę liczb, których wartość należy do zakresu od 3 do 7.</span><span class="sxs-lookup"><span data-stu-id="465c6-136">In the following example, query #7 returns a count of the numbers whose value is between 3 and 7.</span></span> <span data-ttu-id="465c6-137">Ogólnie rzecz biorąc, lepiej jest użyć drugiej zmiennej do przechowywania wyniku wywołania metody.</span><span class="sxs-lookup"><span data-stu-id="465c6-137">In general, however, it is better to use a second variable to store the result of the method call.</span></span> <span data-ttu-id="465c6-138">W ten sposób zapytanie jest mniej podobne do wyników zapytania.</span><span class="sxs-lookup"><span data-stu-id="465c6-138">In this manner, the query is less likely to be confused with the results of the query.</span></span>

[!code-csharp[csProgGuideLINQ#9](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]

<span data-ttu-id="465c6-139">Ponieważ zapytanie #7 zwraca pojedynczą wartość, a nie kolekcję, zapytanie jest wykonywane natychmiast.</span><span class="sxs-lookup"><span data-stu-id="465c6-139">Because Query #7 returns a single value and not a collection, the query executes immediately.</span></span>

<span data-ttu-id="465c6-140">Poprzednie zapytanie można napisać przy użyciu niejawnego wpisywania w `var` , w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="465c6-140">The previous query can be written by using implicit typing with `var`, as follows:</span></span>

```csharp
var numCount = (from num in numbers...
```

<span data-ttu-id="465c6-141">Można je napisać w składni metody w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="465c6-141">It can be written in method syntax as follows:</span></span>

```csharp
var numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

<span data-ttu-id="465c6-142">Można ją napisać przy użyciu jawnego wpisywania w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="465c6-142">It can be written by using explicit typing, as follows:</span></span>

```csharp
int numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

## <a name="see-also"></a><span data-ttu-id="465c6-143">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="465c6-143">See also</span></span>

- [<span data-ttu-id="465c6-144">Przewodnik: Pisanie zapytań w języku C #</span><span class="sxs-lookup"><span data-stu-id="465c6-144">Walkthrough: Writing Queries in C#</span></span>](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)
- [<span data-ttu-id="465c6-145">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="465c6-145">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="465c6-146">Klauzula where</span><span class="sxs-lookup"><span data-stu-id="465c6-146">where clause</span></span>](../language-reference/keywords/where-clause.md)
