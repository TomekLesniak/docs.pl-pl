---
description: Odwołanie do języka C#
title: Odwołanie do języka C#
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: 4712a6906195c5d8bc09c7b734dba0df4d2b08c8
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "89134526"
---
# <a name="into-c-reference"></a><span data-ttu-id="5f667-103">into (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="5f667-103">into (C# Reference)</span></span>

<span data-ttu-id="5f667-104">`into`Kontekstowe słowo kluczowe może służyć do tworzenia tymczasowego identyfikatora do przechowywania wyników [grupy](group-clause.md), [sprzężenia](join-clause.md) lub [zaznaczania](select-clause.md) do nowego identyfikatora.</span><span class="sxs-lookup"><span data-stu-id="5f667-104">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](group-clause.md), [join](join-clause.md) or [select](select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="5f667-105">Ten identyfikator może być generatorem dla dodatkowych poleceń zapytań.</span><span class="sxs-lookup"><span data-stu-id="5f667-105">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="5f667-106">W przypadku użycia w `group` `select` klauzuli OR, użycie nowego identyfikatora jest czasami określane jako *kontynuacja*.</span><span class="sxs-lookup"><span data-stu-id="5f667-106">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>

## <a name="example"></a><span data-ttu-id="5f667-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="5f667-107">Example</span></span>

<span data-ttu-id="5f667-108">W poniższym przykładzie pokazano użycie `into` słowa kluczowego, aby włączyć tymczasowy identyfikator `fruitGroup` , który ma wnioskowany typ `IGrouping` .</span><span class="sxs-lookup"><span data-stu-id="5f667-108">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="5f667-109">Używając identyfikatora, można wywołać <xref:System.Linq.Enumerable.Count%2A> metodę dla każdej grupy i wybrać tylko te grupy, które zawierają dwa lub więcej wyrazów.</span><span class="sxs-lookup"><span data-stu-id="5f667-109">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

<span data-ttu-id="5f667-110">Użycie `into` w `group` klauzuli jest wymagane tylko wtedy, gdy chcesz wykonać dodatkowe operacje na zapytania dla każdej grupy.</span><span class="sxs-lookup"><span data-stu-id="5f667-110">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="5f667-111">Aby uzyskać więcej informacji, zobacz [klauzula](group-clause.md)Group.</span><span class="sxs-lookup"><span data-stu-id="5f667-111">For more information, see [group clause](group-clause.md).</span></span>

<span data-ttu-id="5f667-112">Aby zapoznać się z przykładem użycia `into` w `join` klauzuli, zobacz [Klauzula join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5f667-112">For an example of the use of `into` in a `join` clause, see [join clause](join-clause.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5f667-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5f667-113">See also</span></span>

- [<span data-ttu-id="5f667-114">Słowa kluczowe zapytania (LINQ)</span><span class="sxs-lookup"><span data-stu-id="5f667-114">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="5f667-115">LINQ w C#</span><span class="sxs-lookup"><span data-stu-id="5f667-115">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="5f667-116">group — Klauzula</span><span class="sxs-lookup"><span data-stu-id="5f667-116">group clause</span></span>](group-clause.md)
