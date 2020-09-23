---
title: Operacje kwantyfikatora
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: 0c1c69cb36ac16126454dc0c24cd84fc85b0b218
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075307"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="e20d3-102">Operacje kwantyfikatora (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e20d3-102">Quantifier Operations (Visual Basic)</span></span>

<span data-ttu-id="e20d3-103">Operacje kwantyfikatora zwracają <xref:System.Boolean> wartość wskazującą, czy niektóre lub wszystkie elementy w sekwencji spełniają warunek.</span><span class="sxs-lookup"><span data-stu-id="e20d3-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="e20d3-104">Na poniższej ilustracji przedstawiono dwa różne operacje kwantyfikatora dla dwóch różnych sekwencji źródłowych.</span><span class="sxs-lookup"><span data-stu-id="e20d3-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="e20d3-105">Pierwsza operacja pyta, czy co najmniej jeden element jest znakiem "A", a wynikiem jest `true` .</span><span class="sxs-lookup"><span data-stu-id="e20d3-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="e20d3-106">Druga operacja pyta, czy wszystkie elementy są znakiem "A", a wynik jest `true` .</span><span class="sxs-lookup"><span data-stu-id="e20d3-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Operacje kwantyfikatora LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="e20d3-108">Standardowe metody operatorów zapytań, które wykonują operacje kwantyfikatora, są wymienione w poniższej sekcji.</span><span class="sxs-lookup"><span data-stu-id="e20d3-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e20d3-109">Metody</span><span class="sxs-lookup"><span data-stu-id="e20d3-109">Methods</span></span>  
  
|<span data-ttu-id="e20d3-110">Nazwa metody</span><span class="sxs-lookup"><span data-stu-id="e20d3-110">Method Name</span></span>|<span data-ttu-id="e20d3-111">Opis</span><span class="sxs-lookup"><span data-stu-id="e20d3-111">Description</span></span>|<span data-ttu-id="e20d3-112">Składnia wyrażenia zapytania Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e20d3-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="e20d3-113">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="e20d3-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="e20d3-114">Wszystko</span><span class="sxs-lookup"><span data-stu-id="e20d3-114">All</span></span>|<span data-ttu-id="e20d3-115">Określa, czy wszystkie elementy w sekwencji spełniają warunek.</span><span class="sxs-lookup"><span data-stu-id="e20d3-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e20d3-116">Dowolne</span><span class="sxs-lookup"><span data-stu-id="e20d3-116">Any</span></span>|<span data-ttu-id="e20d3-117">Określa, czy dowolne elementy w sekwencji spełniają warunek.</span><span class="sxs-lookup"><span data-stu-id="e20d3-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e20d3-118">Contains</span><span class="sxs-lookup"><span data-stu-id="e20d3-118">Contains</span></span>|<span data-ttu-id="e20d3-119">Określa, czy sekwencja zawiera określony element.</span><span class="sxs-lookup"><span data-stu-id="e20d3-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="e20d3-120">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="e20d3-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="e20d3-121">Przykłady składni wyrażeń zapytania</span><span class="sxs-lookup"><span data-stu-id="e20d3-121">Query Expression Syntax Examples</span></span>  

 <span data-ttu-id="e20d3-122">W poniższych przykładach użyto `Aggregate` klauzuli w Visual Basic jako części warunku filtrowania w zapytaniu LINQ.</span><span class="sxs-lookup"><span data-stu-id="e20d3-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="e20d3-123">W poniższym przykładzie zastosowano `Aggregate` klauzulę i <xref:System.Linq.Enumerable.All%2A> metodę rozszerzającą, aby zwrócić z kolekcji te osoby, których zwierzęta domowe są starsze niż określony wiek.</span><span class="sxs-lookup"><span data-stu-id="e20d3-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#1)]  
  
 <span data-ttu-id="e20d3-124">W następnym przykładzie zastosowano `Aggregate` klauzulę i <xref:System.Linq.Enumerable.Any%2A> metodę rozszerzającą, aby zwrócić z kolekcji te osoby, które mają co najmniej jedną PET, która jest starsza od określonego wieku.</span><span class="sxs-lookup"><span data-stu-id="e20d3-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e20d3-125">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e20d3-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="e20d3-126">Standardowe operatory zapytań — Omówienie (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e20d3-126">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="e20d3-127">Aggregate, klauzula</span><span class="sxs-lookup"><span data-stu-id="e20d3-127">Aggregate Clause</span></span>](../../../language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="e20d3-128">Instrukcje: zapytanie o zdania zawierające określony zestaw wyrazów (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e20d3-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
