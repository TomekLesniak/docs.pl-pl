---
title: Operacje kwantyfikatora (C#)
description: Dowiedz się więcej o operacjach kwantyfikatora. Te operacje zwracają wartość logiczną wskazującą, czy niektóre lub wszystkie elementy w sekwencji spełniają warunek.
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: ce06f887d3ad7b10cbdedf9e33072df2c0819ef1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299152"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="6c7d5-104">Operacje kwantyfikatora (C#)</span><span class="sxs-lookup"><span data-stu-id="6c7d5-104">Quantifier Operations (C#)</span></span>
<span data-ttu-id="6c7d5-105">Operacje kwantyfikatora zwracają <xref:System.Boolean> wartość wskazującą, czy niektóre lub wszystkie elementy w sekwencji spełniają warunek.</span><span class="sxs-lookup"><span data-stu-id="6c7d5-105">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="6c7d5-106">Na poniższej ilustracji przedstawiono dwa różne operacje kwantyfikatora dla dwóch różnych sekwencji źródłowych.</span><span class="sxs-lookup"><span data-stu-id="6c7d5-106">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="6c7d5-107">Pierwsza operacja pyta, czy co najmniej jeden element jest znakiem "A", a wynikiem jest `true` .</span><span class="sxs-lookup"><span data-stu-id="6c7d5-107">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="6c7d5-108">Druga operacja pyta, czy wszystkie elementy są znakiem "A", a wynik jest `true` .</span><span class="sxs-lookup"><span data-stu-id="6c7d5-108">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![Operacje kwantyfikatora LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="6c7d5-110">Standardowe metody operatorów zapytań, które wykonują operacje kwantyfikatora, są wymienione w poniższej sekcji.</span><span class="sxs-lookup"><span data-stu-id="6c7d5-110">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6c7d5-111">Metody</span><span class="sxs-lookup"><span data-stu-id="6c7d5-111">Methods</span></span>  
  
|<span data-ttu-id="6c7d5-112">Nazwa metody</span><span class="sxs-lookup"><span data-stu-id="6c7d5-112">Method Name</span></span>|<span data-ttu-id="6c7d5-113">Opis</span><span class="sxs-lookup"><span data-stu-id="6c7d5-113">Description</span></span>|<span data-ttu-id="6c7d5-114">Składnia wyrażenia zapytania C#</span><span class="sxs-lookup"><span data-stu-id="6c7d5-114">C# Query Expression Syntax</span></span>|<span data-ttu-id="6c7d5-115">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="6c7d5-115">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="6c7d5-116">Wszystko</span><span class="sxs-lookup"><span data-stu-id="6c7d5-116">All</span></span>|<span data-ttu-id="6c7d5-117">Określa, czy wszystkie elementy w sekwencji spełniają warunek.</span><span class="sxs-lookup"><span data-stu-id="6c7d5-117">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="6c7d5-118">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="6c7d5-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="6c7d5-119">Dowolne</span><span class="sxs-lookup"><span data-stu-id="6c7d5-119">Any</span></span>|<span data-ttu-id="6c7d5-120">Określa, czy dowolne elementy w sekwencji spełniają warunek.</span><span class="sxs-lookup"><span data-stu-id="6c7d5-120">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="6c7d5-121">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="6c7d5-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="6c7d5-122">Contains</span><span class="sxs-lookup"><span data-stu-id="6c7d5-122">Contains</span></span>|<span data-ttu-id="6c7d5-123">Określa, czy sekwencja zawiera określony element.</span><span class="sxs-lookup"><span data-stu-id="6c7d5-123">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="6c7d5-124">Nie dotyczy.</span><span class="sxs-lookup"><span data-stu-id="6c7d5-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="6c7d5-125">Przykłady składni wyrażeń zapytania</span><span class="sxs-lookup"><span data-stu-id="6c7d5-125">Query Expression Syntax Examples</span></span>  
  
### <a name="all"></a><span data-ttu-id="6c7d5-126">Wszystko</span><span class="sxs-lookup"><span data-stu-id="6c7d5-126">All</span></span>  
<span data-ttu-id="6c7d5-127">W poniższym przykładzie używa `All` się do sprawdzenia, czy wszystkie ciągi mają określoną długość.</span><span class="sxs-lookup"><span data-stu-id="6c7d5-127">The following example uses the `All` to check that all strings are of a specific length.</span></span>
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a><span data-ttu-id="6c7d5-128">Dowolne</span><span class="sxs-lookup"><span data-stu-id="6c7d5-128">Any</span></span>  
<span data-ttu-id="6c7d5-129">W poniższym przykładzie używa `Any` się do sprawdzenia, czy wszystkie ciągi zaczynają się od "o".</span><span class="sxs-lookup"><span data-stu-id="6c7d5-129">The following example uses the `Any` to check that any strings are start with 'o'.</span></span>  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a><span data-ttu-id="6c7d5-130">Contains</span><span class="sxs-lookup"><span data-stu-id="6c7d5-130">Contains</span></span>  
<span data-ttu-id="6c7d5-131">W poniższym przykładzie używa `Contains` się do sprawdzenia, czy tablica zawiera określony element.</span><span class="sxs-lookup"><span data-stu-id="6c7d5-131">The following example uses the `Contains` to check an array have a specific element.</span></span>  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a><span data-ttu-id="6c7d5-132">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6c7d5-132">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="6c7d5-133">Standardowe operatory zapytań — Omówienie (C#)</span><span class="sxs-lookup"><span data-stu-id="6c7d5-133">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="6c7d5-134">Dynamiczne określanie filtrów predykatów w środowisku uruchomieniowym</span><span class="sxs-lookup"><span data-stu-id="6c7d5-134">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="6c7d5-135">Jak wykonać zapytanie o zdania zawierające określony zestaw wyrazów (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="6c7d5-135">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
