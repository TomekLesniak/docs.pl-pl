---
title: Sortowanie danych (C#)
description: Informacje o operacjach sortowania i standardowych metodach operatora zapytań, które wykonują operacje sortowania w LINQ w języku C#.
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 5feeb0e2229fc370fdcb9608817f41832bffd7cc
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302337"
---
# <a name="sorting-data-c"></a><span data-ttu-id="5697c-103">Sortowanie danych (C#)</span><span class="sxs-lookup"><span data-stu-id="5697c-103">Sorting Data (C#)</span></span>
<span data-ttu-id="5697c-104">Operacja sortowania Porządkuje elementy sekwencji na podstawie jednego lub większej liczby atrybutów.</span><span class="sxs-lookup"><span data-stu-id="5697c-104">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="5697c-105">Pierwsze kryterium sortowania wykonuje podstawowe sortowanie elementów.</span><span class="sxs-lookup"><span data-stu-id="5697c-105">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="5697c-106">Określając drugie kryterium sortowania, można sortować elementy w ramach każdej podstawowej grupy sortowania.</span><span class="sxs-lookup"><span data-stu-id="5697c-106">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="5697c-107">Na poniższej ilustracji przedstawiono wyniki alfabetycznej operacji sortowania na sekwencji znaków:</span><span class="sxs-lookup"><span data-stu-id="5697c-107">The following illustration shows the results of an alphabetical sort operation on a sequence of characters:</span></span>
  
 ![Grafika pokazująca alfabetyczną operację sortowania.](./media/sorting-data/alphabetical-sort-operation.png)  
  
 <span data-ttu-id="5697c-109">Standardowe metody operatorów zapytań, które sortują dane, są wymienione w poniższej sekcji.</span><span class="sxs-lookup"><span data-stu-id="5697c-109">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5697c-110">Metody</span><span class="sxs-lookup"><span data-stu-id="5697c-110">Methods</span></span>  
  
|<span data-ttu-id="5697c-111">Nazwa metody</span><span class="sxs-lookup"><span data-stu-id="5697c-111">Method Name</span></span>|<span data-ttu-id="5697c-112">Opis</span><span class="sxs-lookup"><span data-stu-id="5697c-112">Description</span></span>|<span data-ttu-id="5697c-113">Składnia wyrażenia zapytania C#</span><span class="sxs-lookup"><span data-stu-id="5697c-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="5697c-114">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="5697c-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="5697c-115">OrderBy</span><span class="sxs-lookup"><span data-stu-id="5697c-115">OrderBy</span></span>|<span data-ttu-id="5697c-116">Sortuje wartości w kolejności rosnącej.</span><span class="sxs-lookup"><span data-stu-id="5697c-116">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="5697c-117">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="5697c-117">OrderByDescending</span></span>|<span data-ttu-id="5697c-118">Sortuje wartości w kolejności malejącej.</span><span class="sxs-lookup"><span data-stu-id="5697c-118">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="5697c-119">ThenBy</span><span class="sxs-lookup"><span data-stu-id="5697c-119">ThenBy</span></span>|<span data-ttu-id="5697c-120">Wykonuje sortowanie pomocnicze w kolejności rosnącej.</span><span class="sxs-lookup"><span data-stu-id="5697c-120">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="5697c-121">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="5697c-121">ThenByDescending</span></span>|<span data-ttu-id="5697c-122">Wykonuje sortowanie pomocnicze w kolejności malejącej.</span><span class="sxs-lookup"><span data-stu-id="5697c-122">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="5697c-123">Reverse</span><span class="sxs-lookup"><span data-stu-id="5697c-123">Reverse</span></span>|<span data-ttu-id="5697c-124">Odwraca kolejność elementów w kolekcji.</span><span class="sxs-lookup"><span data-stu-id="5697c-124">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="5697c-125">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="5697c-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="5697c-126">Przykłady składni wyrażeń zapytania</span><span class="sxs-lookup"><span data-stu-id="5697c-126">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="5697c-127">Główne przykłady sortowania</span><span class="sxs-lookup"><span data-stu-id="5697c-127">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="5697c-128">Podstawowe sortowanie rosnące</span><span class="sxs-lookup"><span data-stu-id="5697c-128">Primary Ascending Sort</span></span>  
 <span data-ttu-id="5697c-129">Poniższy przykład ilustruje sposób użycia `orderby` klauzuli w zapytaniu LINQ do sortowania ciągów w tablicy według długości ciągu w kolejności rosnącej.</span><span class="sxs-lookup"><span data-stu-id="5697c-129">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    brown  
    jumps  
*/  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="5697c-130">Sortowanie sortowania podstawowego</span><span class="sxs-lookup"><span data-stu-id="5697c-130">Primary Descending Sort</span></span>  
 <span data-ttu-id="5697c-131">W następnym przykładzie pokazano, jak używać `orderby descending` klauzuli w zapytaniu LINQ do sortowania ciągów według ich pierwszej litery, w kolejności malejącej.</span><span class="sxs-lookup"><span data-stu-id="5697c-131">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    quick  
    jumps  
    fox  
    brown  
*/  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="5697c-132">Przykłady sortowania pomocniczego</span><span class="sxs-lookup"><span data-stu-id="5697c-132">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="5697c-133">Sortowanie pomocnicze rosnąco</span><span class="sxs-lookup"><span data-stu-id="5697c-133">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="5697c-134">Poniższy przykład ilustruje sposób użycia `orderby` klauzuli w zapytaniu LINQ do wykonywania podstawowego i pomocniczego sortowania ciągów w tablicy.</span><span class="sxs-lookup"><span data-stu-id="5697c-134">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="5697c-135">Ciągi są sortowane głównie według długości i secondarily przez pierwszą literę ciągu, zarówno w kolejności rosnącej.</span><span class="sxs-lookup"><span data-stu-id="5697c-135">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1)  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    fox  
    the  
    brown  
    jumps  
    quick  
*/  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="5697c-136">Sortowanie malejąco</span><span class="sxs-lookup"><span data-stu-id="5697c-136">Secondary Descending Sort</span></span>  
 <span data-ttu-id="5697c-137">W następnym przykładzie pokazano, jak używać `orderby descending` klauzuli w zapytaniu LINQ do wykonywania sortowania podstawowego w kolejności rosnącej i sortowania pomocniczego w kolejności malejącej.</span><span class="sxs-lookup"><span data-stu-id="5697c-137">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="5697c-138">Ciągi są sortowane głównie według długości i secondarily przez pierwszą literę ciągu.</span><span class="sxs-lookup"><span data-stu-id="5697c-138">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    jumps  
    brown  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="5697c-139">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5697c-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="5697c-140">Standardowe operatory zapytań — Omówienie (C#)</span><span class="sxs-lookup"><span data-stu-id="5697c-140">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="5697c-141">Klauzula orderby</span><span class="sxs-lookup"><span data-stu-id="5697c-141">orderby clause</span></span>](../../../language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="5697c-142">Kolejność wyników klauzuli join</span><span class="sxs-lookup"><span data-stu-id="5697c-142">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="5697c-143">Sortowanie lub filtrowanie danych tekstowych według dowolnego wyrazu lub pola (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="5697c-143">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
