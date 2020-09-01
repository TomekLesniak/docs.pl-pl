---
description: Informacje o instrukcji try-catch-finally-C#
title: Informacje o instrukcji try-catch-finally-C#
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 6e85330e12c53e0728ef671530709748090ebe02
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142014"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="14e83-103">try-catch-finally (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="14e83-103">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="14e83-104">Typowym zastosowaniem `catch` i `finally` razem jest uzyskanie zasobów i korzystanie z nich w `try` bloku, zaradzenie sobie z wyjątkowymi okolicznościami w `catch` bloku i zwolnienie zasobów w `finally` bloku.</span><span class="sxs-lookup"><span data-stu-id="14e83-104">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="14e83-105">Aby uzyskać więcej informacji i przykładów dotyczących ponownego zgłaszania wyjątków, zobacz [try-catch](try-catch.md) i [wyrzucanie wyjątków](../../../standard/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="14e83-105">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="14e83-106">Aby uzyskać więcej informacji na temat `finally` bloku, zobacz [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="14e83-106">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="14e83-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="14e83-107">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="14e83-108">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="14e83-108">C# language specification</span></span>

<span data-ttu-id="14e83-109">Aby uzyskać więcej informacji, zobacz sekcję [try instrukcji](~/_csharplang/spec/statements.md#the-try-statement) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="14e83-109">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="14e83-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="14e83-110">See also</span></span>

- [<span data-ttu-id="14e83-111">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="14e83-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="14e83-112">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="14e83-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="14e83-113">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="14e83-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="14e83-114">Instrukcje try, throw i catch (C++)</span><span class="sxs-lookup"><span data-stu-id="14e83-114">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="14e83-115">throw</span><span class="sxs-lookup"><span data-stu-id="14e83-115">throw</span></span>](throw.md)
- [<span data-ttu-id="14e83-116">Instrukcje: Jawne zgłaszanie wyjątków</span><span class="sxs-lookup"><span data-stu-id="14e83-116">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="14e83-117">using, instrukcja</span><span class="sxs-lookup"><span data-stu-id="14e83-117">using Statement</span></span>](using-statement.md)
