---
description: Break, instrukcja (odwołanie w C#)
title: Break, instrukcja (odwołanie w C#)
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 7fd05889f684f7a2282de8222e1195898dead5b9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134747"
---
# <a name="break-c-reference"></a><span data-ttu-id="bb8ee-103">break (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="bb8ee-103">break (C# Reference)</span></span>

<span data-ttu-id="bb8ee-104">`break`Instrukcja kończy najbliższą otaczającą pętlę lub instrukcję [Switch](./switch.md) , w której występuje.</span><span class="sxs-lookup"><span data-stu-id="bb8ee-104">The `break` statement terminates the closest enclosing loop or [switch](./switch.md) statement in which it appears.</span></span> <span data-ttu-id="bb8ee-105">Kontrolka jest przenoszona do instrukcji, która następuje po instrukcji zakończony (jeśli istnieje).</span><span class="sxs-lookup"><span data-stu-id="bb8ee-105">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="bb8ee-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="bb8ee-106">Example</span></span>

<span data-ttu-id="bb8ee-107">W tym przykładzie Instrukcja warunkowa zawiera licznik, który powinien być liczony od 1 do 100; Jednakże `break` instrukcja kończy pętlę po 4 zliczenia.</span><span class="sxs-lookup"><span data-stu-id="bb8ee-107">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="bb8ee-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="bb8ee-108">Example</span></span>

<span data-ttu-id="bb8ee-109">Ten przykład ilustruje użycie `break` w instrukcji [Switch](./switch.md) .</span><span class="sxs-lookup"><span data-stu-id="bb8ee-109">This example demonstrates the use of `break` in a [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="bb8ee-110">W przypadku wprowadzenia `4` danych wyjściowych będzie:</span><span class="sxs-lookup"><span data-stu-id="bb8ee-110">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="example"></a><span data-ttu-id="bb8ee-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="bb8ee-111">Example</span></span>

<span data-ttu-id="bb8ee-112">W tym przykładzie `break` instrukcja jest używana do przerywania wewnętrznej pętli zagnieżdżonej i zwracania kontroli do pętli zewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="bb8ee-112">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span> <span data-ttu-id="bb8ee-113">Formant jest zwracany _tylko_ jeden poziom w pętli zagnieżdżonych.</span><span class="sxs-lookup"><span data-stu-id="bb8ee-113">Control is _only_ returned one level up in the nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="bb8ee-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="bb8ee-114">Example</span></span>

<span data-ttu-id="bb8ee-115">W tym przykładzie `break` instrukcja jest używana tylko do rozbicia z bieżącej gałęzi podczas każdej iteracji pętli.</span><span class="sxs-lookup"><span data-stu-id="bb8ee-115">In this example, the `break` statement is only used to break out of the current branch during each iteration of the loop.</span></span> <span data-ttu-id="bb8ee-116">Wystąpienia należące do samej pętli nie mają wpływ na `break` zagnieżdżoną instrukcję [Switch](./switch.md) .</span><span class="sxs-lookup"><span data-stu-id="bb8ee-116">The loop itself is unaffected by the instances of `break` that belong to the nested [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="bb8ee-117">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="bb8ee-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="bb8ee-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bb8ee-118">See also</span></span>

- [<span data-ttu-id="bb8ee-119">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="bb8ee-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bb8ee-120">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="bb8ee-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bb8ee-121">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="bb8ee-121">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="bb8ee-122">przełącznika</span><span class="sxs-lookup"><span data-stu-id="bb8ee-122">switch</span></span>](./switch.md)
