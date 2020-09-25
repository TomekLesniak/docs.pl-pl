---
title: Operacje Set (C#)
description: Dowiedz się więcej na temat operacji ustawiania i standardowych metod operatora zapytań, które wykonują operacje Set w LINQ w języku C#.
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 8679f804adaaeada390206e3e1dd2a0711a2cbf6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195613"
---
# <a name="set-operations-c"></a><span data-ttu-id="b0a34-103">Operacje Set (C#)</span><span class="sxs-lookup"><span data-stu-id="b0a34-103">Set Operations (C#)</span></span>

<span data-ttu-id="b0a34-104">Operacje Set w LINQ odnoszą się do operacji zapytania, które tworzą zestaw wyników, który jest oparty na obecności lub braku równoważnych elementów w obrębie tych samych lub oddzielnych kolekcji (lub zestawów).</span><span class="sxs-lookup"><span data-stu-id="b0a34-104">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="b0a34-105">W poniższej sekcji przedstawiono standardowe metody operatorów zapytań, które wykonują operacje na zestawach.</span><span class="sxs-lookup"><span data-stu-id="b0a34-105">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b0a34-106">Metody</span><span class="sxs-lookup"><span data-stu-id="b0a34-106">Methods</span></span>  
  
|<span data-ttu-id="b0a34-107">Nazwa metody</span><span class="sxs-lookup"><span data-stu-id="b0a34-107">Method Name</span></span>|<span data-ttu-id="b0a34-108">Opis</span><span class="sxs-lookup"><span data-stu-id="b0a34-108">Description</span></span>|<span data-ttu-id="b0a34-109">Składnia wyrażenia zapytania C#</span><span class="sxs-lookup"><span data-stu-id="b0a34-109">C# Query Expression Syntax</span></span>|<span data-ttu-id="b0a34-110">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="b0a34-110">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="b0a34-111">Distinct</span><span class="sxs-lookup"><span data-stu-id="b0a34-111">Distinct</span></span>|<span data-ttu-id="b0a34-112">Usuwa zduplikowane wartości z kolekcji.</span><span class="sxs-lookup"><span data-stu-id="b0a34-112">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="b0a34-113">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="b0a34-113">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b0a34-114">Z wyjątkiem</span><span class="sxs-lookup"><span data-stu-id="b0a34-114">Except</span></span>|<span data-ttu-id="b0a34-115">Zwraca różnicę zestawu, co oznacza elementy jednej kolekcji, które nie znajdują się w drugiej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="b0a34-115">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="b0a34-116">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="b0a34-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b0a34-117">Wspólnej</span><span class="sxs-lookup"><span data-stu-id="b0a34-117">Intersect</span></span>|<span data-ttu-id="b0a34-118">Zwraca część wspólną, która oznacza elementy, które pojawiają się w każdej z dwóch kolekcji.</span><span class="sxs-lookup"><span data-stu-id="b0a34-118">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="b0a34-119">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="b0a34-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b0a34-120">Unia</span><span class="sxs-lookup"><span data-stu-id="b0a34-120">Union</span></span>|<span data-ttu-id="b0a34-121">Zwraca zestaw zbiorów, co oznacza unikatowe elementy, które pojawiają się w jednej z dwóch kolekcji.</span><span class="sxs-lookup"><span data-stu-id="b0a34-121">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="b0a34-122">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="b0a34-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="b0a34-123">Porównanie operacji ustawiania</span><span class="sxs-lookup"><span data-stu-id="b0a34-123">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="b0a34-124">Distinct</span><span class="sxs-lookup"><span data-stu-id="b0a34-124">Distinct</span></span>  

 <span data-ttu-id="b0a34-125">Poniższy przykład przedstawia zachowanie <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> metody dla sekwencji znaków.</span><span class="sxs-lookup"><span data-stu-id="b0a34-125">The following example depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="b0a34-126">Zwracana sekwencja zawiera unikatowe elementy z sekwencji wejściowej.</span><span class="sxs-lookup"><span data-stu-id="b0a34-126">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![Ilustracja przedstawiająca zachowanie odrębnych&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)  

 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a><span data-ttu-id="b0a34-128">Z wyjątkiem</span><span class="sxs-lookup"><span data-stu-id="b0a34-128">Except</span></span>  

 <span data-ttu-id="b0a34-129">W poniższym przykładzie przedstawiono zachowanie <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="b0a34-129">The following example depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b0a34-130">Zwracana sekwencja zawiera tylko elementy z pierwszej sekwencji wejściowej, które nie znajdują się w drugiej sekwencji wejściowej.</span><span class="sxs-lookup"><span data-stu-id="b0a34-130">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="b0a34-131">![Ilustracja przedstawiająca akcję z wyjątkiem&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Pokazuje zachowanie z wyjątkiem.")</span><span class="sxs-lookup"><span data-stu-id="b0a34-131">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a><span data-ttu-id="b0a34-132">Wspólnej</span><span class="sxs-lookup"><span data-stu-id="b0a34-132">Intersect</span></span>  

 <span data-ttu-id="b0a34-133">W poniższym przykładzie przedstawiono zachowanie <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="b0a34-133">The following example depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b0a34-134">Zwracana sekwencja zawiera elementy, które są wspólne dla obu sekwencji wejściowych.</span><span class="sxs-lookup"><span data-stu-id="b0a34-134">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![Ilustracja przedstawiająca przecięcie dwóch sekwencji.](./media/set-operations/intersection-two-sequences.png)  

[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a><span data-ttu-id="b0a34-136">Unia</span><span class="sxs-lookup"><span data-stu-id="b0a34-136">Union</span></span>  

 <span data-ttu-id="b0a34-137">Poniższy przykład przedstawia operację Union dla dwóch sekwencji znaków.</span><span class="sxs-lookup"><span data-stu-id="b0a34-137">The following example depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="b0a34-138">Zwracana sekwencja zawiera unikatowe elementy z obu sekwencji wejściowych.</span><span class="sxs-lookup"><span data-stu-id="b0a34-138">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![Ilustracja przedstawiająca Unię dwóch sekwencji.](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]

## <a name="see-also"></a><span data-ttu-id="b0a34-140">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b0a34-140">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="b0a34-141">Standardowe operatory zapytań — Omówienie (C#)</span><span class="sxs-lookup"><span data-stu-id="b0a34-141">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="b0a34-142">Łączenie i porównywanie kolekcji ciągów (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="b0a34-142">How to combine and compare string collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="b0a34-143">Jak znaleźć różnice między dwoma listami (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="b0a34-143">How to find the set difference between two lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
