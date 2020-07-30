---
title: Operacje Set (C#)
description: Dowiedz się więcej na temat operacji ustawiania i standardowych metod operatora zapytań, które wykonują operacje Set w LINQ w języku C#.
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: ab2608b267113ad5d47a33e64cd9a5e21496f668
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302376"
---
# <a name="set-operations-c"></a><span data-ttu-id="33506-103">Operacje Set (C#)</span><span class="sxs-lookup"><span data-stu-id="33506-103">Set Operations (C#)</span></span>
<span data-ttu-id="33506-104">Operacje Set w LINQ odnoszą się do operacji zapytania, które tworzą zestaw wyników, który jest oparty na obecności lub braku równoważnych elementów w obrębie tych samych lub oddzielnych kolekcji (lub zestawów).</span><span class="sxs-lookup"><span data-stu-id="33506-104">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="33506-105">W poniższej sekcji przedstawiono standardowe metody operatorów zapytań, które wykonują operacje na zestawach.</span><span class="sxs-lookup"><span data-stu-id="33506-105">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33506-106">Metody</span><span class="sxs-lookup"><span data-stu-id="33506-106">Methods</span></span>  
  
|<span data-ttu-id="33506-107">Nazwa metody</span><span class="sxs-lookup"><span data-stu-id="33506-107">Method Name</span></span>|<span data-ttu-id="33506-108">Opis</span><span class="sxs-lookup"><span data-stu-id="33506-108">Description</span></span>|<span data-ttu-id="33506-109">Składnia wyrażenia zapytania C#</span><span class="sxs-lookup"><span data-stu-id="33506-109">C# Query Expression Syntax</span></span>|<span data-ttu-id="33506-110">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="33506-110">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="33506-111">Distinct</span><span class="sxs-lookup"><span data-stu-id="33506-111">Distinct</span></span>|<span data-ttu-id="33506-112">Usuwa zduplikowane wartości z kolekcji.</span><span class="sxs-lookup"><span data-stu-id="33506-112">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="33506-113">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="33506-113">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="33506-114">Z wyjątkiem</span><span class="sxs-lookup"><span data-stu-id="33506-114">Except</span></span>|<span data-ttu-id="33506-115">Zwraca różnicę zestawu, co oznacza elementy jednej kolekcji, które nie znajdują się w drugiej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="33506-115">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="33506-116">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="33506-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="33506-117">Wspólnej</span><span class="sxs-lookup"><span data-stu-id="33506-117">Intersect</span></span>|<span data-ttu-id="33506-118">Zwraca część wspólną, która oznacza elementy, które pojawiają się w każdej z dwóch kolekcji.</span><span class="sxs-lookup"><span data-stu-id="33506-118">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="33506-119">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="33506-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="33506-120">Unia</span><span class="sxs-lookup"><span data-stu-id="33506-120">Union</span></span>|<span data-ttu-id="33506-121">Zwraca zestaw zbiorów, co oznacza unikatowe elementy, które pojawiają się w jednej z dwóch kolekcji.</span><span class="sxs-lookup"><span data-stu-id="33506-121">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="33506-122">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="33506-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="33506-123">Porównanie operacji ustawiania</span><span class="sxs-lookup"><span data-stu-id="33506-123">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="33506-124">Distinct</span><span class="sxs-lookup"><span data-stu-id="33506-124">Distinct</span></span>  
 <span data-ttu-id="33506-125">Poniższy przykład przedstawia zachowanie <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> metody dla sekwencji znaków.</span><span class="sxs-lookup"><span data-stu-id="33506-125">The following example depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="33506-126">Zwracana sekwencja zawiera unikatowe elementy z sekwencji wejściowej.</span><span class="sxs-lookup"><span data-stu-id="33506-126">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![Ilustracja przedstawiająca zachowanie odrębnych&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)  

 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a><span data-ttu-id="33506-128">Z wyjątkiem</span><span class="sxs-lookup"><span data-stu-id="33506-128">Except</span></span>  
 <span data-ttu-id="33506-129">W poniższym przykładzie przedstawiono zachowanie <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="33506-129">The following example depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="33506-130">Zwracana sekwencja zawiera tylko elementy z pierwszej sekwencji wejściowej, które nie znajdują się w drugiej sekwencji wejściowej.</span><span class="sxs-lookup"><span data-stu-id="33506-130">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="33506-131">![Ilustracja przedstawiająca akcję z wyjątkiem&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Pokazuje zachowanie z wyjątkiem.")</span><span class="sxs-lookup"><span data-stu-id="33506-131">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a><span data-ttu-id="33506-132">Wspólnej</span><span class="sxs-lookup"><span data-stu-id="33506-132">Intersect</span></span>  
 <span data-ttu-id="33506-133">W poniższym przykładzie przedstawiono zachowanie <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="33506-133">The following example depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="33506-134">Zwracana sekwencja zawiera elementy, które są wspólne dla obu sekwencji wejściowych.</span><span class="sxs-lookup"><span data-stu-id="33506-134">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![Ilustracja przedstawiająca przecięcie dwóch sekwencji.](./media/set-operations/intersection-two-sequences.png)  

[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a><span data-ttu-id="33506-136">Unia</span><span class="sxs-lookup"><span data-stu-id="33506-136">Union</span></span>  
 <span data-ttu-id="33506-137">Poniższy przykład przedstawia operację Union dla dwóch sekwencji znaków.</span><span class="sxs-lookup"><span data-stu-id="33506-137">The following example depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="33506-138">Zwracana sekwencja zawiera unikatowe elementy z obu sekwencji wejściowych.</span><span class="sxs-lookup"><span data-stu-id="33506-138">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![Ilustracja przedstawiająca Unię dwóch sekwencji.](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]

## <a name="see-also"></a><span data-ttu-id="33506-140">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="33506-140">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="33506-141">Standardowe operatory zapytań — Omówienie (C#)</span><span class="sxs-lookup"><span data-stu-id="33506-141">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="33506-142">Łączenie i porównywanie kolekcji ciągów (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="33506-142">How to combine and compare string collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="33506-143">Jak znaleźć różnice między dwoma listami (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="33506-143">How to find the set difference between two lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
