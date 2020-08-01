---
title: 'Funkcje rekurencyjne: rec — Słowo kluczowe'
description: 'Dowiedz się, w jaki sposób słowo kluczowe "Rec" języka F # jest używane z słowem kluczowym "let" w celu zdefiniowania funkcji cyklicznej.'
ms.date: 05/16/2016
ms.openlocfilehash: c2374f90b4585327c6f5208a3d6bca75a23d0cbb
ms.sourcegitcommit: 7499bdb428d63ed0e19e97f54d3d576c41598659
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/31/2020
ms.locfileid: "87455654"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="3c673-103">Funkcje rekurencyjne: rec — Słowo kluczowe</span><span class="sxs-lookup"><span data-stu-id="3c673-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="3c673-104">`rec`Słowo kluczowe jest używane razem ze `let` słowem kluczowym w celu zdefiniowania funkcji cyklicznej.</span><span class="sxs-lookup"><span data-stu-id="3c673-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="3c673-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="3c673-105">Syntax</span></span>

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a><span data-ttu-id="3c673-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3c673-106">Remarks</span></span>

<span data-ttu-id="3c673-107">Funkcje cykliczne, funkcje, które wywołuje siebie, są jawnie identyfikowane w języku F #.</span><span class="sxs-lookup"><span data-stu-id="3c673-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="3c673-108">Dzięki temu identyfikator jest definiowany w zakresie funkcji.</span><span class="sxs-lookup"><span data-stu-id="3c673-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="3c673-109">Poniższy kod ilustruje funkcję cykliczną, która oblicza n- *n*<sup>ty</sup> numer Fibonacci przy użyciu definicji matematycznej.</span><span class="sxs-lookup"><span data-stu-id="3c673-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number using the mathematical definition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="3c673-110">W ćwiczenia, kod, taki jak poprzedni przykład, nie jest idealnym rozwiązaniem, ponieważ unecessarily ponownie oblicza wartości, które zostały już obliczone.</span><span class="sxs-lookup"><span data-stu-id="3c673-110">In practice, code like the previous sample is not ideal because it unecessarily recomputes values that have already been computed.</span></span> <span data-ttu-id="3c673-111">Jest to spowodowane tym, że nie jest to cykliczne zakończenie, co zostało wyjaśnione w dalszej części tego artykułu.</span><span class="sxs-lookup"><span data-stu-id="3c673-111">This is because it is not tail recursive, which is explained further in this article.</span></span>

<span data-ttu-id="3c673-112">Metody są niejawnie cykliczne w obrębie typu; nie ma potrzeby dodawania `rec` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="3c673-112">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="3c673-113">Zezwól na powiązania w klasach niejawnie cyklicznie.</span><span class="sxs-lookup"><span data-stu-id="3c673-113">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="tail-recursion"></a><span data-ttu-id="3c673-114">Rekursja ogona</span><span class="sxs-lookup"><span data-stu-id="3c673-114">Tail recursion</span></span>

<span data-ttu-id="3c673-115">W przypadku niektórych funkcji cyklicznych należy resłużyć do refaktoryzacji bardziej "czystej" definicji dla jednej, która jest [cykliczna](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion).</span><span class="sxs-lookup"><span data-stu-id="3c673-115">For some recursive functions, it is necessary to refactor a more "pure" definition to one that is [tail recursive](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion).</span></span> <span data-ttu-id="3c673-116">Zapobiega to niepotrzebnemu ponownemu obliczaniu.</span><span class="sxs-lookup"><span data-stu-id="3c673-116">This prevents unnecessary recomputations.</span></span> <span data-ttu-id="3c673-117">Na przykład poprzedni generator numerów Fibonacci można napisać ponownie w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="3c673-117">For example, the previous fibonacci number generator can be rewritten like this:</span></span>

```fsharp
let fib n =
    let rec loop acc1 acc2 n =
        match n with
        | 0 -> acc1
        | 1 -> acc2
        | _ ->
            loop acc2 (acc1 + acc2) (n - 1)
    loop 0 1 n
```

<span data-ttu-id="3c673-118">Jest to bardziej skomplikowana implementacja.</span><span class="sxs-lookup"><span data-stu-id="3c673-118">This is a more complicated implementation.</span></span> <span data-ttu-id="3c673-119">Generowanie numeru Fibonacci to doskonały przykład algorytmu "algorytmie", który jest matematycznie czysty, ale niewydajny.</span><span class="sxs-lookup"><span data-stu-id="3c673-119">Generating a fibonacci number is a great example of a "naive" algorithm that's mathematically pure but inefficient in practice.</span></span> <span data-ttu-id="3c673-120">Kilka aspektów sprawia, że jest to wydajne w języku F #, a pozostałe zdefiniowane cyklicznie:</span><span class="sxs-lookup"><span data-stu-id="3c673-120">Several aspects make it efficient in F# while still remaining recursively defined:</span></span>

* <span data-ttu-id="3c673-121">Cykliczna funkcja wewnętrzna o nazwie `loop` , która jest wzorcem języka F # idiomatyczne.</span><span class="sxs-lookup"><span data-stu-id="3c673-121">A recursive inner function named `loop`, which is an idiomatic F# pattern.</span></span>
* <span data-ttu-id="3c673-122">Dwa parametry modułu, które są przekazywane wartości do wywołań cyklicznych.</span><span class="sxs-lookup"><span data-stu-id="3c673-122">Two accumulator parameters, which pass accumulate values to recursive calls.</span></span>
* <span data-ttu-id="3c673-123">Sprawdzenie wartości `n` w celu zwrócenia określonego akumulacji.</span><span class="sxs-lookup"><span data-stu-id="3c673-123">A check on the value of `n` to return a specific accumulate.</span></span>

<span data-ttu-id="3c673-124">Jeśli ten przykład został zapisaną iteracyjnie przy użyciu pętli, kod będzie wyglądać podobnie z dwoma różnymi wartościami sumowania liczb do momentu spełnienia określonego warunku.</span><span class="sxs-lookup"><span data-stu-id="3c673-124">If this example were written iteratively with a loop, the code would look similar with two different values accumulating numbers until a particular condition was met.</span></span>

<span data-ttu-id="3c673-125">Powód, dla którego jest to cykliczne, jest spowodowane tym, że wywołanie cykliczne nie musi zapisywać żadnych wartości w stosie wywołań.</span><span class="sxs-lookup"><span data-stu-id="3c673-125">The reason why this is tail-recursive is because the recursive call does not need to save any values on the call stack.</span></span> <span data-ttu-id="3c673-126">Wszystkie obliczane wartości pośrednie są sumowane za pośrednictwem danych wejściowych funkcji wewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="3c673-126">All intermediate values being calculated are accumulated via inputs to the inner function.</span></span> <span data-ttu-id="3c673-127">Pozwala to również kompilatorowi języka F # zoptymalizować kod tak szybko, jakby Zapisano coś takiego jak `while` pętla.</span><span class="sxs-lookup"><span data-stu-id="3c673-127">This also allows the F# compiler to optimize the code to be just as fast as if you had written something like a `while` loop.</span></span>

<span data-ttu-id="3c673-128">Często należy napisać kod języka F #, który cyklicznie przetwarza coś przy użyciu funkcji wewnętrznej i zewnętrznej, jak pokazano w poprzednim przykładzie.</span><span class="sxs-lookup"><span data-stu-id="3c673-128">It's common to write F# code that recursively processes something with an inner and outer function, as the previous example shows.</span></span> <span data-ttu-id="3c673-129">Funkcja wewnętrzna używa rekursji tail, natomiast funkcja zewnętrzna ma lepszy interfejs dla wywołań.</span><span class="sxs-lookup"><span data-stu-id="3c673-129">The inner function uses tail recursion, while the outer function has a better interface for callers.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="3c673-130">Funkcje wzajemnie cykliczne</span><span class="sxs-lookup"><span data-stu-id="3c673-130">Mutually Recursive Functions</span></span>

<span data-ttu-id="3c673-131">Czasami funkcje są *wzajemnie cykliczne*, co oznacza, że wywołuje postać okręgu, w którym jedna funkcja wywołuje inną funkcję, która z kolei wywołuje pierwszy, z dowolną liczbą wywołań między.</span><span class="sxs-lookup"><span data-stu-id="3c673-131">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="3c673-132">Należy zdefiniować takie funkcje razem w jednym `let` powiązaniu, używając `and` słowa kluczowego, aby połączyć je ze sobą.</span><span class="sxs-lookup"><span data-stu-id="3c673-132">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="3c673-133">Poniższy przykład pokazuje dwie funkcje wzajemnie cykliczne.</span><span class="sxs-lookup"><span data-stu-id="3c673-133">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="3c673-134">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3c673-134">See also</span></span>

- [<span data-ttu-id="3c673-135">Funkcje</span><span class="sxs-lookup"><span data-stu-id="3c673-135">Functions</span></span>](index.md)
