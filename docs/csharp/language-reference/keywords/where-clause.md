---
description: klauzula WHERE — odwołanie w C#
title: klauzula WHERE — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: 58a8dc226bb2720b6a8251f028712a80f74e893c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "89141689"
---
# <a name="where-clause-c-reference"></a><span data-ttu-id="5eb81-103">Klauzula where (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="5eb81-103">where clause (C# Reference)</span></span>

<span data-ttu-id="5eb81-104">`where`Klauzula jest używana w wyrażeniu zapytania, aby określić, które elementy ze źródła danych będą zwracane w wyrażeniu zapytania.</span><span class="sxs-lookup"><span data-stu-id="5eb81-104">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="5eb81-105">Stosuje warunek logiczny (*predykat*) do każdego elementu źródłowego (do którego odwołuje się zmienna zakresu) i zwraca te, dla których określony warunek ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="5eb81-105">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="5eb81-106">Pojedyncze wyrażenie zapytania może zawierać wiele `where` klauzul, a pojedyncza klauzula może zawierać wiele podwyrażeń predykatu.</span><span class="sxs-lookup"><span data-stu-id="5eb81-106">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>

## <a name="example"></a><span data-ttu-id="5eb81-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="5eb81-107">Example</span></span>

<span data-ttu-id="5eb81-108">W poniższym przykładzie `where` klauzula filtruje wszystkie liczby z wyjątkiem tych, które są mniejsze niż pięć.</span><span class="sxs-lookup"><span data-stu-id="5eb81-108">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="5eb81-109">Usunięcie `where` klauzuli spowoduje zwrócenie wszystkich liczb ze źródła danych.</span><span class="sxs-lookup"><span data-stu-id="5eb81-109">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="5eb81-110">Wyrażenie `num < 5` jest predykatem, który jest stosowany do każdego elementu.</span><span class="sxs-lookup"><span data-stu-id="5eb81-110">The expression `num < 5` is the predicate that is applied to each element.</span></span>

[!code-csharp[cscsrefQueryKeywords#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#5)]

## <a name="example"></a><span data-ttu-id="5eb81-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="5eb81-111">Example</span></span>

<span data-ttu-id="5eb81-112">W obrębie jednej `where` klauzuli można określić dowolną liczbę predykatów, używając [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) operatorów i [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) .</span><span class="sxs-lookup"><span data-stu-id="5eb81-112">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) and [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="5eb81-113">W poniższym przykładzie zapytanie określa dwa predykaty w celu wybrania tylko liczb parzystych mniejszych niż pięć.</span><span class="sxs-lookup"><span data-stu-id="5eb81-113">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>

[!code-csharp[cscsrefQueryKeywords#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#6)]  

## <a name="example"></a><span data-ttu-id="5eb81-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="5eb81-114">Example</span></span>

<span data-ttu-id="5eb81-115">`where`Klauzula może zawierać jedną lub więcej metod, które zwracają wartości logiczne.</span><span class="sxs-lookup"><span data-stu-id="5eb81-115">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="5eb81-116">W poniższym przykładzie `where` klauzula używa metody, aby określić, czy bieżąca wartość zmiennej zakresu jest parzysta czy nieparzysta.</span><span class="sxs-lookup"><span data-stu-id="5eb81-116">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>

[!code-csharp[cscsrefQueryKeywords#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#7)]

## <a name="remarks"></a><span data-ttu-id="5eb81-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5eb81-117">Remarks</span></span>

<span data-ttu-id="5eb81-118">`where`Klauzula jest mechanizmem filtrowania.</span><span class="sxs-lookup"><span data-stu-id="5eb81-118">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="5eb81-119">Można ją umieścić niemal w dowolnym miejscu w wyrażeniu zapytania, z wyjątkiem sytuacji, w której nie może być pierwszą lub ostatnią klauzulą.</span><span class="sxs-lookup"><span data-stu-id="5eb81-119">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="5eb81-120">`where`Klauzula może pojawić się przed lub po klauzuli [Group](group-clause.md) w zależności od tego, czy konieczne jest Filtrowanie elementów źródłowych przed lub po zgrupowaniu.</span><span class="sxs-lookup"><span data-stu-id="5eb81-120">A `where` clause may appear either before or after a [group](group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>

<span data-ttu-id="5eb81-121">Jeśli określony predykat jest nieprawidłowy dla elementów w źródle danych, zostanie zwrócony błąd czasu kompilacji.</span><span class="sxs-lookup"><span data-stu-id="5eb81-121">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="5eb81-122">Jest to jedna korzyść ze ścisłego sprawdzania typu zapewnianego przez LINQ.</span><span class="sxs-lookup"><span data-stu-id="5eb81-122">This is one benefit of the strong type-checking provided by LINQ.</span></span>

<span data-ttu-id="5eb81-123">W czasie kompilacji `where` słowo kluczowe jest konwertowane na wywołanie <xref:System.Linq.Enumerable.Where%2A> metody standardowego operatora zapytań.</span><span class="sxs-lookup"><span data-stu-id="5eb81-123">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>

## <a name="see-also"></a><span data-ttu-id="5eb81-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5eb81-124">See also</span></span>

- [<span data-ttu-id="5eb81-125">Słowa kluczowe zapytania (LINQ)</span><span class="sxs-lookup"><span data-stu-id="5eb81-125">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="5eb81-126">Klauzula From</span><span class="sxs-lookup"><span data-stu-id="5eb81-126">from clause</span></span>](from-clause.md)
- [<span data-ttu-id="5eb81-127">select — Klauzula</span><span class="sxs-lookup"><span data-stu-id="5eb81-127">select clause</span></span>](select-clause.md)
- [<span data-ttu-id="5eb81-128">Filtrowanie danych</span><span class="sxs-lookup"><span data-stu-id="5eb81-128">Filtering Data</span></span>](../../programming-guide/concepts/linq/filtering-data.md)
- [<span data-ttu-id="5eb81-129">LINQ w C#</span><span class="sxs-lookup"><span data-stu-id="5eb81-129">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="5eb81-130">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="5eb81-130">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
