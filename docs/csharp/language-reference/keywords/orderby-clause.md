---
description: OrderBy — klauzula — odwołanie w C#
title: OrderBy — klauzula — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: 2f64b45ff252c7cc02e56c465da21ccc5e861aec
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142352"
---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="ceb99-103">Klauzula orderby (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="ceb99-103">orderby clause (C# Reference)</span></span>

<span data-ttu-id="ceb99-104">W wyrażeniu zapytania, `orderby` klauzula powoduje, że zwracana sekwencja lub podsekwencja (Grupa) ma być sortowana w kolejności rosnącej lub malejącej.</span><span class="sxs-lookup"><span data-stu-id="ceb99-104">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="ceb99-105">Można określić wiele kluczy, aby wykonać jedną lub więcej pomocniczych operacji sortowania.</span><span class="sxs-lookup"><span data-stu-id="ceb99-105">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="ceb99-106">Sortowanie jest wykonywane przez domyślną funkcję porównującą dla typu elementu.</span><span class="sxs-lookup"><span data-stu-id="ceb99-106">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="ceb99-107">Domyślna kolejność sortowania to Ascending.</span><span class="sxs-lookup"><span data-stu-id="ceb99-107">The default sort order is ascending.</span></span> <span data-ttu-id="ceb99-108">Można również określić niestandardową funkcję porównującą.</span><span class="sxs-lookup"><span data-stu-id="ceb99-108">You can also specify a custom comparer.</span></span> <span data-ttu-id="ceb99-109">Jednak jest on dostępny tylko przy użyciu składni opartej na metodzie.</span><span class="sxs-lookup"><span data-stu-id="ceb99-109">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="ceb99-110">Aby uzyskać więcej informacji, zobacz [Sortowanie danych](../../programming-guide/concepts/linq/sorting-data.md).</span><span class="sxs-lookup"><span data-stu-id="ceb99-110">For more information, see [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md).</span></span>

## <a name="example"></a><span data-ttu-id="ceb99-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="ceb99-111">Example</span></span>

<span data-ttu-id="ceb99-112">W poniższym przykładzie pierwsze zapytanie sortuje wyrazy w kolejności alfabetycznej, zaczynając od A, a drugie zapytanie sortuje te same wyrazy w kolejności malejącej.</span><span class="sxs-lookup"><span data-stu-id="ceb99-112">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="ceb99-113">( `ascending` Słowo kluczowe jest domyślną wartością sortowania i można je pominąć).</span><span class="sxs-lookup"><span data-stu-id="ceb99-113">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a><span data-ttu-id="ceb99-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="ceb99-114">Example</span></span>

<span data-ttu-id="ceb99-115">Poniższy przykład wykonuje sortowanie podstawowe dla nazwisk uczniów, a następnie pomocnicze sortowanie według ich imion.</span><span class="sxs-lookup"><span data-stu-id="ceb99-115">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a><span data-ttu-id="ceb99-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ceb99-116">Remarks</span></span>

<span data-ttu-id="ceb99-117">W czasie kompilacji `orderby` klauzula jest tłumaczona na wywołanie <xref:System.Linq.Enumerable.OrderBy%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="ceb99-117">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="ceb99-118">Wiele kluczy w `orderby` klauzuli jest przetłumaczyć na <xref:System.Linq.Enumerable.ThenBy%2A> wywołania metod.</span><span class="sxs-lookup"><span data-stu-id="ceb99-118">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="ceb99-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ceb99-119">See also</span></span>

- [<span data-ttu-id="ceb99-120">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="ceb99-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ceb99-121">Słowa kluczowe zapytania (LINQ)</span><span class="sxs-lookup"><span data-stu-id="ceb99-121">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="ceb99-122">LINQ w C#</span><span class="sxs-lookup"><span data-stu-id="ceb99-122">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="ceb99-123">group — Klauzula</span><span class="sxs-lookup"><span data-stu-id="ceb99-123">group clause</span></span>](group-clause.md)
- [<span data-ttu-id="ceb99-124">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="ceb99-124">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
