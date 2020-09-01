---
description: goto — instrukcja — odwołanie w C#
title: goto — instrukcja — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: de95e477bd7e76f549130643c8d4b70a0e2f015c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128429"
---
# <a name="goto-c-reference"></a><span data-ttu-id="8e5d2-103">goto (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="8e5d2-103">goto (C# Reference)</span></span>

<span data-ttu-id="8e5d2-104">`goto`Instrukcja przesyła bezpośrednio kontrolę programu do instrukcji oznaczonej etykietą.</span><span class="sxs-lookup"><span data-stu-id="8e5d2-104">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="8e5d2-105">Typowym zastosowaniem `goto` jest przeniesienie kontroli do określonej etykiety przypadku przełącznika lub etykiety domyślnej w `switch` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="8e5d2-105">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="8e5d2-106">`goto`Instrukcja jest również przydatna do uzyskiwania z głęboko zagnieżdżonych pętli.</span><span class="sxs-lookup"><span data-stu-id="8e5d2-106">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="8e5d2-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="8e5d2-107">Example</span></span>

<span data-ttu-id="8e5d2-108">Poniższy przykład demonstruje użycie `goto` w instrukcji [Switch](switch.md) .</span><span class="sxs-lookup"><span data-stu-id="8e5d2-108">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="8e5d2-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="8e5d2-109">Example</span></span>

<span data-ttu-id="8e5d2-110">Poniższy przykład ilustruje użycie polecenia `goto` , aby wydzielić z zagnieżdżonych pętli.</span><span class="sxs-lookup"><span data-stu-id="8e5d2-110">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="8e5d2-111">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="8e5d2-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="8e5d2-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8e5d2-112">See also</span></span>

- [<span data-ttu-id="8e5d2-113">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="8e5d2-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8e5d2-114">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="8e5d2-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8e5d2-115">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="8e5d2-115">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="8e5d2-116">goto, instrukcja (C++)</span><span class="sxs-lookup"><span data-stu-id="8e5d2-116">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)
