---
description: SELECT — odwołanie w C#
title: SELECT — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- select_CSharpKeyword
- select
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
ms.openlocfilehash: d67c99cc841c08a63cc83843a07a46e80199b9d1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "89136905"
---
# <a name="select-clause-c-reference"></a><span data-ttu-id="49c13-103">select — Klauzula (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="49c13-103">select clause (C# Reference)</span></span>

<span data-ttu-id="49c13-104">W wyrażeniu zapytania `select` klauzula określa typ wartości, które zostaną utworzone podczas wykonywania zapytania.</span><span class="sxs-lookup"><span data-stu-id="49c13-104">In a query expression, the `select` clause specifies the type of values that will be produced when the query is executed.</span></span> <span data-ttu-id="49c13-105">Wynik jest oparty na ocenie wszystkich poprzednich klauzul i w dowolnych wyrażeniach w `select` samej klauzuli.</span><span class="sxs-lookup"><span data-stu-id="49c13-105">The result is based on the evaluation of all the previous clauses and on any expressions in the `select` clause itself.</span></span> <span data-ttu-id="49c13-106">Wyrażenie zapytania musi kończyć się `select` klauzulą lub [grupą](group-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="49c13-106">A query expression must terminate with either a `select` clause or a [group](group-clause.md) clause.</span></span>

<span data-ttu-id="49c13-107">Poniższy przykład pokazuje prostą `select` klauzulę w wyrażeniu zapytania.</span><span class="sxs-lookup"><span data-stu-id="49c13-107">The following example shows a simple `select` clause in a query expression.</span></span>

[!code-csharp[cscsrefQueryKeywords#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#8)]  

<span data-ttu-id="49c13-108">Typ sekwencji utworzonej przez `select` klauzulę określa typ zmiennej zapytania `queryHighScores` .</span><span class="sxs-lookup"><span data-stu-id="49c13-108">The type of the sequence produced by the `select` clause determines the type of the query variable `queryHighScores`.</span></span> <span data-ttu-id="49c13-109">W najprostszym przypadku `select` klauzula określa tylko zmienną zakresu.</span><span class="sxs-lookup"><span data-stu-id="49c13-109">In the simplest case, the `select` clause just specifies the range variable.</span></span> <span data-ttu-id="49c13-110">Powoduje to, że zwracana sekwencja zawiera elementy tego samego typu co źródło danych.</span><span class="sxs-lookup"><span data-stu-id="49c13-110">This causes the returned sequence to contain elements of the same type as the data source.</span></span> <span data-ttu-id="49c13-111">Aby uzyskać więcej informacji, zobacz temat [relacje typu w operacjach zapytań LINQ](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="49c13-111">For more information, see [Type Relationships in LINQ Query Operations](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span> <span data-ttu-id="49c13-112">Jednak `select` klauzula zawiera również zaawansowany mechanizm przekształcania (lub *projekcji*) danych źródłowych na nowe typy.</span><span class="sxs-lookup"><span data-stu-id="49c13-112">However, the `select` clause also provides a powerful mechanism for transforming (or *projecting*) source data into new types.</span></span> <span data-ttu-id="49c13-113">Aby uzyskać więcej informacji, zobacz [Przekształcanie danych za pomocą LINQ (C#)](../../programming-guide/concepts/linq/data-transformations-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="49c13-113">For more information, see [Data Transformations with LINQ (C#)](../../programming-guide/concepts/linq/data-transformations-with-linq.md).</span></span>

## <a name="example"></a><span data-ttu-id="49c13-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="49c13-114">Example</span></span>

<span data-ttu-id="49c13-115">W poniższym przykładzie pokazano wszystkie różne formy, które `select` mogą wykonać klauzula.</span><span class="sxs-lookup"><span data-stu-id="49c13-115">The following example shows all the different forms that a `select` clause may take.</span></span> <span data-ttu-id="49c13-116">W każdym zapytaniu Zwróć uwagę na relacje między `select` klauzulą i typem *zmiennej zapytania* ( `studentQuery1` , `studentQuery2` itd.).</span><span class="sxs-lookup"><span data-stu-id="49c13-116">In each query, note the relationship between the `select` clause and the type of the *query variable* (`studentQuery1`, `studentQuery2`, and so on).</span></span>

[!code-csharp[cscsrefQueryKeywords#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#9)]

<span data-ttu-id="49c13-117">Jak pokazano w `studentQuery8` poprzednim przykładzie, czasami warto chcieć, aby elementy zwracanej sekwencji zawierały tylko podzestaw właściwości elementów źródłowych.</span><span class="sxs-lookup"><span data-stu-id="49c13-117">As shown in `studentQuery8` in the previous example, sometimes you might want the elements of the returned sequence to contain only a subset of the properties of the source elements.</span></span> <span data-ttu-id="49c13-118">Przez pozostawienie zwróconej sekwencji jak najmniejszej ilości, można zmniejszyć wymagania dotyczące pamięci i zwiększyć szybkość wykonywania zapytania.</span><span class="sxs-lookup"><span data-stu-id="49c13-118">By keeping the returned sequence as small as possible you can reduce the memory requirements and increase the speed of the execution of the query.</span></span> <span data-ttu-id="49c13-119">Można to zrobić przez utworzenie typu anonimowego w `select` klauzuli i użycie inicjatora obiektów w celu zainicjowania go z odpowiednimi właściwościami z elementu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="49c13-119">You can accomplish this by creating an anonymous type in the `select` clause and using an object initializer to initialize it with the appropriate properties from the source element.</span></span> <span data-ttu-id="49c13-120">Aby uzyskać przykład, jak to zrobić, zobacz [Inicjatory obiektów i kolekcji](../../programming-guide/classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="49c13-120">For an example of how to do this, see [Object and Collection Initializers](../../programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="49c13-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="49c13-121">Remarks</span></span>

<span data-ttu-id="49c13-122">W czasie kompilacji `select` klauzula jest tłumaczona na wywołanie metody do <xref:System.Linq.Enumerable.Select%2A> standardowego operatora zapytań.</span><span class="sxs-lookup"><span data-stu-id="49c13-122">At compile time, the `select` clause is translated to a method call to the <xref:System.Linq.Enumerable.Select%2A> standard query operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="49c13-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="49c13-123">See also</span></span>

- [<span data-ttu-id="49c13-124">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="49c13-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="49c13-125">Słowa kluczowe zapytania (LINQ)</span><span class="sxs-lookup"><span data-stu-id="49c13-125">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="49c13-126">Klauzula From</span><span class="sxs-lookup"><span data-stu-id="49c13-126">from clause</span></span>](from-clause.md)
- [<span data-ttu-id="49c13-127">częściowe (Metoda) (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="49c13-127">partial (Method) (C# Reference)</span></span>](partial-method.md)
- [<span data-ttu-id="49c13-128">Typy anonimowe</span><span class="sxs-lookup"><span data-stu-id="49c13-128">Anonymous Types</span></span>](../../programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="49c13-129">LINQ w C#</span><span class="sxs-lookup"><span data-stu-id="49c13-129">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="49c13-130">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="49c13-130">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
