---
title: var — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: d944cde932b5c1f5ef1439ee46a1447e107e6ac9
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053078"
---
# <a name="var-c-reference"></a><span data-ttu-id="d3219-102">var (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="d3219-102">var (C# Reference)</span></span>

<span data-ttu-id="d3219-103">Począwszy od języka Visual C# 3,0, zmienne, które są zadeklarowane w zakresie metody, mogą mieć niejawny typ "Type" `var` .</span><span class="sxs-lookup"><span data-stu-id="d3219-103">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="d3219-104">Niejawnie wpisana zmienna lokalna jest silnie wpisana, tak jakby zadeklarowano typ samodzielnie, ale kompilator określa typ.</span><span class="sxs-lookup"><span data-stu-id="d3219-104">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="d3219-105">Następujące dwie deklaracje `i` są funkcjonalnie równoważne:</span><span class="sxs-lookup"><span data-stu-id="d3219-105">The following two declarations of `i` are functionally equivalent:</span></span>

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

<span data-ttu-id="d3219-106">Aby uzyskać więcej informacji, zobacz [niejawnie wpisane zmienne lokalne](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) i [relacje typu w operacjach zapytań LINQ](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="d3219-106">For more information, see [Implicitly Typed Local Variables](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3219-107">Gdy `var` jest używany z włączonymi typami odwołań dopuszczających wartość null, zawsze implikuje typ referencyjny dopuszczający wartość null, nawet jeśli typ wyrażenia nie dopuszcza wartości null.</span><span class="sxs-lookup"><span data-stu-id="d3219-107">When `var` is used with nullable reference types enabled, it always implies a nullable reference type even if the expression type isn't nullable.</span></span>

## <a name="example"></a><span data-ttu-id="d3219-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="d3219-108">Example</span></span>

<span data-ttu-id="d3219-109">Poniższy przykład przedstawia dwa wyrażenia zapytania.</span><span class="sxs-lookup"><span data-stu-id="d3219-109">The following example shows two query expressions.</span></span> <span data-ttu-id="d3219-110">W pierwszym wyrażeniu użycie `var` jest dozwolone, ale nie jest wymagane, ponieważ typ wyniku zapytania może być jawnie określony jako `IEnumerable<string>` .</span><span class="sxs-lookup"><span data-stu-id="d3219-110">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="d3219-111">Jednak w drugim wyrażeniu, `var` umożliwia wynik jako Kolekcja typów anonimowych, a nazwa tego typu jest niedostępna z wyjątkiem kompilatora.</span><span class="sxs-lookup"><span data-stu-id="d3219-111">However, in the second expression, `var` allows the result to be a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="d3219-112">Użycie `var` eliminuje wymóg tworzenia nowej klasy dla wyniku.</span><span class="sxs-lookup"><span data-stu-id="d3219-112">Use of `var` eliminates the requirement to create a new class for the result.</span></span> <span data-ttu-id="d3219-113">Należy zauważyć, że w przykładzie #2 `foreach` Zmienna iteracji `item` również musi być wpisana niejawnie.</span><span class="sxs-lookup"><span data-stu-id="d3219-113">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a><span data-ttu-id="d3219-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d3219-114">See also</span></span>

- [<span data-ttu-id="d3219-115">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="d3219-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d3219-116">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="d3219-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d3219-117">Jawnie wpisana zmienna lokalna</span><span class="sxs-lookup"><span data-stu-id="d3219-117">Implicitly Typed Local Variables</span></span>](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
