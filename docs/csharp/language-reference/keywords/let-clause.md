---
description: klauzula Let — odwołanie w C#
title: klauzula Let — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: 3767b9745cccd9802374a8100de19f286c9b55ea
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139596"
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="84062-103">Klauzula Let (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="84062-103">let clause (C# Reference)</span></span>

<span data-ttu-id="84062-104">W wyrażeniu zapytania czasami warto przechowywać wynik wyrażenia podrzędnego w celu użycia go w kolejnych klauzulach.</span><span class="sxs-lookup"><span data-stu-id="84062-104">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="84062-105">Można to zrobić za pomocą `let` słowa kluczowego, które tworzy nową zmienną zakresu i inicjuje ją z wynikiem podania wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="84062-105">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="84062-106">Po zainicjowaniu z wartością zmienna zakresu nie może być używana do przechowywania innej wartości.</span><span class="sxs-lookup"><span data-stu-id="84062-106">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="84062-107">Jeśli jednak zmienna zakresu zawiera typ queryable, może to być zapytanie.</span><span class="sxs-lookup"><span data-stu-id="84062-107">However, if the range variable holds a queryable type, it can be queried.</span></span>

## <a name="example"></a><span data-ttu-id="84062-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="84062-108">Example</span></span>

<span data-ttu-id="84062-109">W poniższym przykładzie `let` jest używany na dwa sposoby:</span><span class="sxs-lookup"><span data-stu-id="84062-109">In the following example `let` is used in two ways:</span></span>

1. <span data-ttu-id="84062-110">Aby utworzyć wyliczalny typ, który może być badany.</span><span class="sxs-lookup"><span data-stu-id="84062-110">To create an enumerable type that can itself be queried.</span></span>

2. <span data-ttu-id="84062-111">Aby włączyć wywoływanie zapytania `ToLower` tylko raz dla zmiennej zakresu `word` .</span><span class="sxs-lookup"><span data-stu-id="84062-111">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="84062-112">Bez użycia `let` , należy wywołać `ToLower` każdy predykat w `where` klauzuli.</span><span class="sxs-lookup"><span data-stu-id="84062-112">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a><span data-ttu-id="84062-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="84062-113">See also</span></span>

- [<span data-ttu-id="84062-114">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="84062-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="84062-115">Słowa kluczowe zapytania (LINQ)</span><span class="sxs-lookup"><span data-stu-id="84062-115">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="84062-116">LINQ w C#</span><span class="sxs-lookup"><span data-stu-id="84062-116">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="84062-117">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="84062-117">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="84062-118">Obsługa wyjątków w wyrażeniach zapytań</span><span class="sxs-lookup"><span data-stu-id="84062-118">Handle exceptions in query expressions</span></span>](../../linq/handle-exceptions-in-query-expressions.md)
