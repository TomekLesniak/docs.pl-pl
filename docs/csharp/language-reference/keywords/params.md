---
description: params — słowo kluczowe dla tablic parametrów — odwołanie w C#
title: params — słowo kluczowe dla tablic parametrów — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
- parameter array
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: a2726c725508cd297001aaabddeff414704d1115
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134474"
---
# <a name="params-c-reference"></a><span data-ttu-id="df505-103">params (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="df505-103">params (C# Reference)</span></span>

<span data-ttu-id="df505-104">Za pomocą `params` słowa kluczowego, można określić [parametr metody](method-parameters.md) , który przyjmuje zmienną liczbę argumentów.</span><span class="sxs-lookup"><span data-stu-id="df505-104">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span> <span data-ttu-id="df505-105">Typ parametru musi być tablicą jednowymiarową.</span><span class="sxs-lookup"><span data-stu-id="df505-105">The parameter type must be a single-dimensional array.</span></span>

<span data-ttu-id="df505-106">Żadne dodatkowe parametry nie są dozwolone po `params` słowie kluczowym w deklaracji metody i tylko jedno `params` słowo kluczowe jest dozwolone w deklaracji metody.</span><span class="sxs-lookup"><span data-stu-id="df505-106">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="df505-107">Jeśli zadeklarowany typ `params` parametru nie jest tablicą jednowymiarową, wystąpi błąd kompilatora [CS0225](../../misc/cs0225.md) .</span><span class="sxs-lookup"><span data-stu-id="df505-107">If the declared type of the `params` parameter is not a single-dimensional array, compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

<span data-ttu-id="df505-108">Po wywołaniu metody z `params` parametrem można przekazać:</span><span class="sxs-lookup"><span data-stu-id="df505-108">When you call a method with a `params` parameter, you can pass in:</span></span>

- <span data-ttu-id="df505-109">Rozdzielana przecinkami lista argumentów typu elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="df505-109">A comma-separated list of arguments of the type of the array elements.</span></span>
- <span data-ttu-id="df505-110">Tablica argumentów określonego typu.</span><span class="sxs-lookup"><span data-stu-id="df505-110">An array of arguments of the specified type.</span></span>
- <span data-ttu-id="df505-111">Brak argumentów.</span><span class="sxs-lookup"><span data-stu-id="df505-111">No arguments.</span></span> <span data-ttu-id="df505-112">Jeśli nie wyślesz żadnych argumentów, długość `params` listy wynosi zero.</span><span class="sxs-lookup"><span data-stu-id="df505-112">If you send no arguments, the length of the `params` list is zero.</span></span>

## <a name="example"></a><span data-ttu-id="df505-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="df505-113">Example</span></span>

<span data-ttu-id="df505-114">Poniższy przykład ilustruje różne sposoby wysyłania argumentów do `params` parametru.</span><span class="sxs-lookup"><span data-stu-id="df505-114">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="df505-115">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="df505-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="df505-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="df505-116">See also</span></span>

- [<span data-ttu-id="df505-117">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="df505-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="df505-118">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="df505-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="df505-119">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="df505-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="df505-120">Parametry metody</span><span class="sxs-lookup"><span data-stu-id="df505-120">Method Parameters</span></span>](method-parameters.md)
