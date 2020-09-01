---
description: gdy kontekstowe słowo kluczowe — odwołanie w C#
title: gdy kontekstowe słowo kluczowe — odwołanie w C#
ms.date: 03/07/2017
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
ms.openlocfilehash: bd3a7beeb7d3c4b62d6b70e2b1c6f38ab4b6804f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138218"
---
# <a name="when-c-reference"></a><span data-ttu-id="0bca3-103">When (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="0bca3-103">when (C# Reference)</span></span>

<span data-ttu-id="0bca3-104">Możesz użyć `when` kontekstowego słowa kluczowego, aby określić warunek filtru w następujących kontekstach:</span><span class="sxs-lookup"><span data-stu-id="0bca3-104">You can use the `when` contextual keyword to specify a filter condition in the following contexts:</span></span>

- <span data-ttu-id="0bca3-105">W `catch` instrukcji bloku [try/catch](try-catch.md) lub [try/catch/finally](try-catch-finally.md) .</span><span class="sxs-lookup"><span data-stu-id="0bca3-105">In the `catch` statement of a [try/catch](try-catch.md) or [try/catch/finally](try-catch-finally.md) block.</span></span>
- <span data-ttu-id="0bca3-106">W `case` etykiecie instrukcji [Switch](switch.md) .</span><span class="sxs-lookup"><span data-stu-id="0bca3-106">In the `case` label of a [switch](switch.md) statement.</span></span>
- <span data-ttu-id="0bca3-107">W [ `switch` wyrażeniu](../operators/switch-expression.md).</span><span class="sxs-lookup"><span data-stu-id="0bca3-107">In the [`switch` expression](../operators/switch-expression.md).</span></span>

## <a name="when-in-a-catch-statement"></a><span data-ttu-id="0bca3-108">`when` w `catch` instrukcji</span><span class="sxs-lookup"><span data-stu-id="0bca3-108">`when` in a `catch` statement</span></span>

<span data-ttu-id="0bca3-109">Począwszy od języka C# 6, `when` można użyć w `catch` instrukcji, aby określić warunek, który musi mieć wartość true dla programu obsługi określonego wyjątku do wykonania.</span><span class="sxs-lookup"><span data-stu-id="0bca3-109">Starting with C# 6, `when` can be used in a `catch` statement to specify a condition that must be true for the handler for a specific exception to execute.</span></span> <span data-ttu-id="0bca3-110">Jego składnia to:</span><span class="sxs-lookup"><span data-stu-id="0bca3-110">Its syntax is:</span></span>

```csharp
catch (ExceptionType [e]) when (expr)
```

<span data-ttu-id="0bca3-111">gdzie *Expr* jest wyrażeniem, którego wynikiem jest wartość logiczna.</span><span class="sxs-lookup"><span data-stu-id="0bca3-111">where *expr* is an expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="0bca3-112">Jeśli zwróci `true` , program obsługi wyjątków jest wykonywany; Jeśli nie jest `false` .</span><span class="sxs-lookup"><span data-stu-id="0bca3-112">If it returns `true`, the exception handler executes; if `false`, it does not.</span></span>

<span data-ttu-id="0bca3-113">Poniższy przykład używa `when` słowa kluczowego, aby warunkowo wykonywać procedury obsługi w <xref:System.Net.Http.HttpRequestException> zależności od tekstu komunikatu o wyjątku.</span><span class="sxs-lookup"><span data-stu-id="0bca3-113">The following example uses the `when` keyword to conditionally execute handlers for an <xref:System.Net.Http.HttpRequestException> depending on the text of the exception message.</span></span>

[!code-csharp[when-with-catch](~/samples/snippets/csharp/language-reference/keywords/when/catch.cs)]

## <a name="when-in-a-switch-statement"></a><span data-ttu-id="0bca3-114">`when` w `switch` instrukcji</span><span class="sxs-lookup"><span data-stu-id="0bca3-114">`when` in a `switch` statement</span></span>

<span data-ttu-id="0bca3-115">Począwszy od języka C# 7,0, `case` etykiety nie muszą być wzajemnie wykluczane, a kolejność, w jakiej `case` etykiety pojawiają się w `switch` instrukcji, może ustalić, który blok przełącznika jest wykonywany.</span><span class="sxs-lookup"><span data-stu-id="0bca3-115">Starting with C# 7.0, `case` labels no longer need be mutually exclusive, and the order in which `case` labels appear in a `switch` statement can determine which switch block executes.</span></span> <span data-ttu-id="0bca3-116">Za pomocą `when` słowa kluczowego można określić warunek filtru, który powoduje, że skojarzona z nim etykieta Case ma wartość true tylko wtedy, gdy warunek filtru ma również wartość true.</span><span class="sxs-lookup"><span data-stu-id="0bca3-116">The `when` keyword can be used to specify a filter condition that causes its associated case label to be true only if the filter condition is also true.</span></span> <span data-ttu-id="0bca3-117">Jego składnia to:</span><span class="sxs-lookup"><span data-stu-id="0bca3-117">Its syntax is:</span></span>

```csharp
case (expr) when (when-condition):
```

<span data-ttu-id="0bca3-118">gdzie *Expr* jest wzorcem stałej lub wzorcem typu, który jest porównywany z wyrażeniem Match, a *warunek when* jest dowolnym wyrażeniem logicznym.</span><span class="sxs-lookup"><span data-stu-id="0bca3-118">where *expr* is a constant pattern or type pattern that is compared to the match expression, and *when-condition* is any Boolean expression.</span></span>

<span data-ttu-id="0bca3-119">Poniższy przykład używa `when` słowa kluczowego do testowania dla `Shape` obiektów, które mają powierzchnię zero, a także do testowania dla różnych `Shape` obiektów, które mają obszar większy niż zero.</span><span class="sxs-lookup"><span data-stu-id="0bca3-119">The following example uses the `when` keyword to test for `Shape` objects that have an area of zero, as well as to test for a variety of `Shape` objects that have an area greater than zero.</span></span>

[!code-csharp[when-with-case#1](~/samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]

## <a name="see-also"></a><span data-ttu-id="0bca3-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0bca3-120">See also</span></span>

- [<span data-ttu-id="0bca3-121">switch, instrukcja</span><span class="sxs-lookup"><span data-stu-id="0bca3-121">switch statement</span></span>](switch.md)
- [<span data-ttu-id="0bca3-122">Instrukcja try/catch</span><span class="sxs-lookup"><span data-stu-id="0bca3-122">try/catch statement</span></span>](try-catch.md)
- [<span data-ttu-id="0bca3-123">Instrukcja try/catch/finally</span><span class="sxs-lookup"><span data-stu-id="0bca3-123">try/catch/finally statement</span></span>](try-catch-finally.md)
