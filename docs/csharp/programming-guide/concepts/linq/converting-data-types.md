---
title: Konwertowanie typów danych (C#)
description: Metody konwersji zmieniają typ obiektów wejściowych. Zobacz operacje konwersji w zapytaniach LINQ w języku C#, takie jak wyliczalne. AsEnumerable i wyliczalne. OfType.
ms.date: 07/20/2015
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
ms.openlocfilehash: f9e3b354fd6eeba6564067550ea3821e4946d92f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159140"
---
# <a name="converting-data-types-c"></a><span data-ttu-id="b2a6c-104">Konwertowanie typów danych (C#)</span><span class="sxs-lookup"><span data-stu-id="b2a6c-104">Converting Data Types (C#)</span></span>

<span data-ttu-id="b2a6c-105">Metody konwersji zmieniają typ obiektów wejściowych.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-105">Conversion methods change the type of input objects.</span></span>

 <span data-ttu-id="b2a6c-106">Operacje konwersji w zapytaniach LINQ są przydatne w różnych aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-106">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="b2a6c-107">Poniżej przedstawiono kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="b2a6c-107">Following are some examples:</span></span>

- <span data-ttu-id="b2a6c-108"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>Metoda może służyć do ukrycia niestandardowej implementacji standardowego operatora zapytań.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-108">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>

- <span data-ttu-id="b2a6c-109"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType>Metoda może służyć do włączenia kolekcji niesparametryzowanej dla zapytań LINQ.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-109">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>

- <span data-ttu-id="b2a6c-110"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>Metody, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType> , <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> i <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> mogą być używane do wymuszenia natychmiastowego wykonania zapytania zamiast odliczenia go do momentu wyliczenia zapytania.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-110">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>

## <a name="methods"></a><span data-ttu-id="b2a6c-111">Metody</span><span class="sxs-lookup"><span data-stu-id="b2a6c-111">Methods</span></span>

 <span data-ttu-id="b2a6c-112">W poniższej tabeli wymieniono standardowe metody operatorów zapytań, które wykonują konwersje typów danych.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-112">The following table lists the standard query operator methods that perform data-type conversions.</span></span>

 <span data-ttu-id="b2a6c-113">Metody konwersji w tej tabeli, których nazwy zaczynają się od "As", zmieniają typ statyczny kolekcji źródłowej, ale nie są wyliczane.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-113">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="b2a6c-114">Metody, których nazwy zaczynają się od "do", wyliczają kolekcję źródłową i umieszczają elementy w odpowiednim typie kolekcji.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-114">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>

|<span data-ttu-id="b2a6c-115">Nazwa metody</span><span class="sxs-lookup"><span data-stu-id="b2a6c-115">Method Name</span></span>|<span data-ttu-id="b2a6c-116">Opis</span><span class="sxs-lookup"><span data-stu-id="b2a6c-116">Description</span></span>|<span data-ttu-id="b2a6c-117">Składnia wyrażenia zapytania C#</span><span class="sxs-lookup"><span data-stu-id="b2a6c-117">C# Query Expression Syntax</span></span>|<span data-ttu-id="b2a6c-118">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="b2a6c-118">More Information</span></span>|
|-----------------|-----------------|---------------------------------|----------------------|
|<span data-ttu-id="b2a6c-119">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="b2a6c-119">AsEnumerable</span></span>|<span data-ttu-id="b2a6c-120">Zwraca dane wejściowe wpisane jako <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="b2a6c-120">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="b2a6c-121">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b2a6c-122">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="b2a6c-122">AsQueryable</span></span>|<span data-ttu-id="b2a6c-123">Konwertuje (ogólne) <xref:System.Collections.IEnumerable> na (rodzajowy) <xref:System.Linq.IQueryable> .</span><span class="sxs-lookup"><span data-stu-id="b2a6c-123">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="b2a6c-124">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-124">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b2a6c-125">Rzutowanie</span><span class="sxs-lookup"><span data-stu-id="b2a6c-125">Cast</span></span>|<span data-ttu-id="b2a6c-126">Rzutuje elementy kolekcji na określony typ.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-126">Casts the elements of a collection to a specified type.</span></span>|<span data-ttu-id="b2a6c-127">Użyj jawnie wpisanej zmiennej zakresu.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-127">Use an explicitly typed range variable.</span></span> <span data-ttu-id="b2a6c-128">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="b2a6c-128">For example:</span></span><br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b2a6c-129">OfType</span><span class="sxs-lookup"><span data-stu-id="b2a6c-129">OfType</span></span>|<span data-ttu-id="b2a6c-130">Filtruje wartości w zależności od ich zdolności do rzutowania do określonego typu.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-130">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="b2a6c-131">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-131">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b2a6c-132">ToArray —</span><span class="sxs-lookup"><span data-stu-id="b2a6c-132">ToArray</span></span>|<span data-ttu-id="b2a6c-133">Konwertuje kolekcję na tablicę.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-133">Converts a collection to an array.</span></span> <span data-ttu-id="b2a6c-134">Ta metoda wymusza wykonanie zapytania.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-134">This method forces query execution.</span></span>|<span data-ttu-id="b2a6c-135">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b2a6c-136">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="b2a6c-136">ToDictionary</span></span>|<span data-ttu-id="b2a6c-137">Umieszcza elementy w <xref:System.Collections.Generic.Dictionary%602> oparciu o funkcję selektora kluczy.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-137">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="b2a6c-138">Ta metoda wymusza wykonanie zapytania.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-138">This method forces query execution.</span></span>|<span data-ttu-id="b2a6c-139">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-139">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b2a6c-140">ToList —</span><span class="sxs-lookup"><span data-stu-id="b2a6c-140">ToList</span></span>|<span data-ttu-id="b2a6c-141">Konwertuje kolekcję na <xref:System.Collections.Generic.List%601> .</span><span class="sxs-lookup"><span data-stu-id="b2a6c-141">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="b2a6c-142">Ta metoda wymusza wykonanie zapytania.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-142">This method forces query execution.</span></span>|<span data-ttu-id="b2a6c-143">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-143">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b2a6c-144">ToLookup</span><span class="sxs-lookup"><span data-stu-id="b2a6c-144">ToLookup</span></span>|<span data-ttu-id="b2a6c-145">Umieszcza elementy w <xref:System.Linq.Lookup%602> (słownik jeden-do-wielu) w oparciu o funkcję selektora kluczy.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-145">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="b2a6c-146">Ta metoda wymusza wykonanie zapytania.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-146">This method forces query execution.</span></span>|<span data-ttu-id="b2a6c-147">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-147">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="b2a6c-148">Przykład składni wyrażenia zapytania</span><span class="sxs-lookup"><span data-stu-id="b2a6c-148">Query Expression Syntax Example</span></span>

<span data-ttu-id="b2a6c-149">Poniższy przykład kodu używa zmiennej jawnie określonego zakresu do rzutowania typu na podtyp przed uzyskaniem dostępu do elementu członkowskiego, który jest dostępny tylko dla podtypu.</span><span class="sxs-lookup"><span data-stu-id="b2a6c-149">The following code example uses an explicitly typed range variable to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>

```csharp
class Plant
{
    public string Name { get; set; }
}

class CarnivorousPlant : Plant
{
    public string TrapType { get; set; }
}

static void Cast()
{
    Plant[] plants = new Plant[] {
        new CarnivorousPlant { Name = "Venus Fly Trap", TrapType = "Snap Trap" },
        new CarnivorousPlant { Name = "Pitcher Plant", TrapType = "Pitfall Trap" },
        new CarnivorousPlant { Name = "Sundew", TrapType = "Flypaper Trap" },
        new CarnivorousPlant { Name = "Waterwheel Plant", TrapType = "Snap Trap" }
    };

    var query = from CarnivorousPlant cPlant in plants
                where cPlant.TrapType == "Snap Trap"
                select cPlant;

    foreach (Plant plant in query)
        Console.WriteLine(plant.Name);

    /* This code produces the following output:

        Venus Fly Trap
        Waterwheel Plant
    */
}
```

## <a name="see-also"></a><span data-ttu-id="b2a6c-150">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b2a6c-150">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="b2a6c-151">Standardowe operatory zapytań — Omówienie (C#)</span><span class="sxs-lookup"><span data-stu-id="b2a6c-151">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="b2a6c-152">Klauzula from</span><span class="sxs-lookup"><span data-stu-id="b2a6c-152">from clause</span></span>](../../../language-reference/keywords/from-clause.md)
- [<span data-ttu-id="b2a6c-153">Wyrażenia zapytania LINQ</span><span class="sxs-lookup"><span data-stu-id="b2a6c-153">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="b2a6c-154">Jak zbadać ArrayList za pomocą LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="b2a6c-154">How to query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)
