---
description: Return — Instrukcja (odwołanie w C#)
title: Return — Instrukcja (odwołanie w C#)
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 486db846304c0972942ff58f3d5b276083681abe
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137007"
---
# <a name="return-c-reference"></a><span data-ttu-id="30b9e-103">return (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="30b9e-103">return (C# Reference)</span></span>

<span data-ttu-id="30b9e-104">`return`Instrukcja kończy wykonywanie metody, w której występuje i zwraca kontrolę do metody wywołującej.</span><span class="sxs-lookup"><span data-stu-id="30b9e-104">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="30b9e-105">Może również zwrócić wartość opcjonalną.</span><span class="sxs-lookup"><span data-stu-id="30b9e-105">It can also return an optional value.</span></span> <span data-ttu-id="30b9e-106">Jeśli metoda jest `void` typem, `return` instrukcja może zostać pominięta.</span><span class="sxs-lookup"><span data-stu-id="30b9e-106">If the method is a `void` type, the `return` statement can be omitted.</span></span>

 <span data-ttu-id="30b9e-107">Jeśli instrukcja return znajduje się wewnątrz `try` bloku, `finally` blok, jeśli taki istnieje, zostanie wykonany przed powracaniem kontroli do metody wywołującej.</span><span class="sxs-lookup"><span data-stu-id="30b9e-107">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>

## <a name="example"></a><span data-ttu-id="30b9e-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="30b9e-108">Example</span></span>

 <span data-ttu-id="30b9e-109">W poniższym przykładzie metoda `CalculateArea()` zwraca zmienną lokalną `area` jako `double` wartość.</span><span class="sxs-lookup"><span data-stu-id="30b9e-109">In the following example, the method `CalculateArea()` returns the local variable `area` as a `double` value.</span></span>

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="30b9e-110">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="30b9e-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="30b9e-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="30b9e-111">See also</span></span>

- [<span data-ttu-id="30b9e-112">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="30b9e-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="30b9e-113">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="30b9e-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="30b9e-114">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="30b9e-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="30b9e-115">Return — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="30b9e-115">return Statement</span></span>](/cpp/cpp/return-statement-cpp)
