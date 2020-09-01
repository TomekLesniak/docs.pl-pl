---
description: Informacje o instrukcji try-finally-C#
title: Informacje o instrukcji try-finally-C#
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: 621c5bf1607136361b72f978681607ec2aec150f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141975"
---
# <a name="try-finally-c-reference"></a><span data-ttu-id="a3834-103">try-finally (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="a3834-103">try-finally (C# Reference)</span></span>

<span data-ttu-id="a3834-104">Za pomocą `finally` bloku, można wyczyścić wszystkie zasoby, które są przydzielone w bloku [try](try-catch.md) , i można uruchomić kod nawet wtedy, gdy wystąpi wyjątek w `try` bloku.</span><span class="sxs-lookup"><span data-stu-id="a3834-104">By using a `finally` block, you can clean up any resources that are allocated in a [try](try-catch.md) block, and you can run code even if an exception occurs in the `try` block.</span></span> <span data-ttu-id="a3834-105">Zazwyczaj instrukcje bloku są uruchamiane, `finally` gdy kontrolka opuszcza `try` instrukcję.</span><span class="sxs-lookup"><span data-stu-id="a3834-105">Typically, the statements of a `finally` block run when control leaves a `try` statement.</span></span> <span data-ttu-id="a3834-106">Transfer kontroli może wystąpić w wyniku normalnego wykonania, wykonania `break` `continue` instrukcji,, `goto` , lub `return` , lub propagacji wyjątku z `try` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="a3834-106">The transfer of control can occur as a result of normal execution, of execution of a `break`, `continue`, `goto`, or `return` statement, or of propagation of an exception out of the `try` statement.</span></span>

<span data-ttu-id="a3834-107">W ramach obsłużonego wyjątku `finally` zagwarantowany jest, że skojarzony blok jest uruchamiany.</span><span class="sxs-lookup"><span data-stu-id="a3834-107">Within a handled exception, the associated `finally` block is guaranteed to be run.</span></span> <span data-ttu-id="a3834-108">Jeśli jednak wyjątek nie jest obsługiwany, wykonanie `finally` bloku jest zależne od tego, w jaki sposób wyzwalany jest wyjątek operacji unwind.</span><span class="sxs-lookup"><span data-stu-id="a3834-108">However, if the exception is unhandled, execution of the `finally` block is dependent on how the exception unwind operation is triggered.</span></span> <span data-ttu-id="a3834-109">To z kolei zależy od konfiguracji komputera.</span><span class="sxs-lookup"><span data-stu-id="a3834-109">That, in turn, is dependent on how your computer is set up.</span></span>

<span data-ttu-id="a3834-110">Zwykle, gdy nieobsługiwany wyjątek kończący aplikację, niezależnie od tego, czy `finally` blok jest uruchomiony, nie jest ważne.</span><span class="sxs-lookup"><span data-stu-id="a3834-110">Usually, when an unhandled exception ends an application, whether or not the `finally` block is run is not important.</span></span> <span data-ttu-id="a3834-111">Jednakże jeśli istnieją instrukcje w `finally` bloku, który musi być uruchamiany nawet w takiej sytuacji, jedno rozwiązanie ma dodać `catch` blok do `try` - `finally` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="a3834-111">However, if you have statements in a `finally` block that must be run even in that situation, one solution is to add a `catch` block to the `try`-`finally` statement.</span></span> <span data-ttu-id="a3834-112">Alternatywnie można przechwytywać wyjątek, który może zostać wygenerowany w `try` bloku `try` - `finally` instrukcji wyższej w górę stosu wywołań.</span><span class="sxs-lookup"><span data-stu-id="a3834-112">Alternatively, you can catch the exception that might be thrown in the `try` block of a `try`-`finally` statement higher up the call stack.</span></span> <span data-ttu-id="a3834-113">Oznacza to, że można przechwytywać wyjątek w metodzie, która wywołuje metodę, która zawiera `try` - `finally` instrukcję, lub w metodzie, która wywołuje tę metodę, lub w dowolnej metodzie w stosie wywołań.</span><span class="sxs-lookup"><span data-stu-id="a3834-113">That is, you can catch the exception in the method that calls the method that contains the `try`-`finally` statement, or in the method that calls that method, or in any method in the call stack.</span></span> <span data-ttu-id="a3834-114">Jeśli wyjątek nie zostanie przechwycony, wykonanie `finally` bloku zależy od tego, czy system operacyjny wybiera wyzwalacz operacji unwind.</span><span class="sxs-lookup"><span data-stu-id="a3834-114">If the exception is not caught, execution of the `finally` block depends on whether the operating system chooses to trigger an exception unwind operation.</span></span>

## <a name="example"></a><span data-ttu-id="a3834-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="a3834-115">Example</span></span>

<span data-ttu-id="a3834-116">W poniższym przykładzie instrukcja konwersji nieprawidłowa powoduje `System.InvalidCastException` wyjątek.</span><span class="sxs-lookup"><span data-stu-id="a3834-116">In the following example, an invalid conversion statement causes a `System.InvalidCastException` exception.</span></span> <span data-ttu-id="a3834-117">Wyjątek nie jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="a3834-117">The exception is unhandled.</span></span>

[!code-csharp[csrefKeywordsExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#4)]

<span data-ttu-id="a3834-118">W poniższym przykładzie wyjątek z `TryCast` metody jest przechwytywany w metodzie dalej w stosie wywołań.</span><span class="sxs-lookup"><span data-stu-id="a3834-118">In the following example, an exception from the `TryCast` method is caught in a method farther up the call stack.</span></span>

[!code-csharp[csrefKeywordsExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#6)]

<span data-ttu-id="a3834-119">Aby uzyskać więcej informacji na temat `finally` , zobacz [try-catch-finally](try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="a3834-119">For more information about `finally`, see [try-catch-finally](try-catch-finally.md).</span></span>

<span data-ttu-id="a3834-120">C# zawiera również [instrukcję using](using-statement.md), która zapewnia podobną funkcjonalność dla <xref:System.IDisposable> obiektów w wygodnej składni.</span><span class="sxs-lookup"><span data-stu-id="a3834-120">C# also contains the [using statement](using-statement.md), which provides similar functionality for <xref:System.IDisposable> objects in a convenient syntax.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a3834-121">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="a3834-121">C# language specification</span></span>

<span data-ttu-id="a3834-122">Aby uzyskać więcej informacji, zobacz sekcję [try instrukcji](~/_csharplang/spec/statements.md#the-try-statement) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="a3834-122">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a3834-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a3834-123">See also</span></span>

- [<span data-ttu-id="a3834-124">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="a3834-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a3834-125">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="a3834-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a3834-126">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="a3834-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a3834-127">Instrukcje try, throw i catch (C++)</span><span class="sxs-lookup"><span data-stu-id="a3834-127">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="a3834-128">throw</span><span class="sxs-lookup"><span data-stu-id="a3834-128">throw</span></span>](throw.md)
- [<span data-ttu-id="a3834-129">try-catch</span><span class="sxs-lookup"><span data-stu-id="a3834-129">try-catch</span></span>](try-catch.md)
- [<span data-ttu-id="a3834-130">Instrukcje: Jawne zgłaszanie wyjątków</span><span class="sxs-lookup"><span data-stu-id="a3834-130">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
