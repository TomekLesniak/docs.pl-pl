---
description: Domena dostępności — Dokumentacja języka C#
title: Domena dostępności — Dokumentacja języka C#
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 2cfc4cc72a79b33276b7d822a2b31eb518dcf784
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89127064"
---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="f48c0-103">Domena dostępności (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="f48c0-103">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="f48c0-104">Domena dostępności elementu członkowskiego określa, w którym sekcji programu można odwoływać się do elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="f48c0-104">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="f48c0-105">Jeśli element członkowski jest zagnieżdżony w innym typie, jego domena dostępności jest określana przez zarówno [poziom dostępności](./accessibility-levels.md) elementu członkowskiego, jak i domenę dostępności typu natychmiastowego.</span><span class="sxs-lookup"><span data-stu-id="f48c0-105">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](./accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="f48c0-106">Domena dostępności typu najwyższego poziomu jest co najmniej tekstem programu w projekcie, w którym jest zadeklarowana.</span><span class="sxs-lookup"><span data-stu-id="f48c0-106">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="f48c0-107">Oznacza to, że domena zawiera wszystkie pliki źródłowe tego projektu.</span><span class="sxs-lookup"><span data-stu-id="f48c0-107">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="f48c0-108">Domena dostępności typu zagnieżdżonego jest co najmniej tekstem programu typu, w którym jest zadeklarowana.</span><span class="sxs-lookup"><span data-stu-id="f48c0-108">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="f48c0-109">Oznacza to, że domena jest treścią typu, która obejmuje wszystkie typy zagnieżdżone.</span><span class="sxs-lookup"><span data-stu-id="f48c0-109">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="f48c0-110">Domena dostępności typu zagnieżdżonego nigdy nie przekracza typu zawierającego.</span><span class="sxs-lookup"><span data-stu-id="f48c0-110">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="f48c0-111">Te koncepcje przedstawiono w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="f48c0-111">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f48c0-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="f48c0-112">Example</span></span>  
 <span data-ttu-id="f48c0-113">Ten przykład zawiera typ najwyższego poziomu, `T1` i dwie klasy zagnieżdżone `M1` i `M2` .</span><span class="sxs-lookup"><span data-stu-id="f48c0-113">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="f48c0-114">Klasy zawierają pola, które mają inne zadeklarowane podano.</span><span class="sxs-lookup"><span data-stu-id="f48c0-114">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="f48c0-115">W `Main` metodzie komentarz jest zgodny z każdą instrukcją, aby wskazać domenę dostępności każdego elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="f48c0-115">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="f48c0-116">Zwróć uwagę, że instrukcje, które próbują odwołać się do niedostępnych elementów członkowskich, są oznaczone jako komentarz. Jeśli chcesz zobaczyć błędy kompilatora spowodowane odwołaniem do niedostępnego elementu członkowskiego, Usuń Komentarze pojedynczo.</span><span class="sxs-lookup"><span data-stu-id="f48c0-116">Notice that the statements that try to reference the inaccessible members are commented out. If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a><span data-ttu-id="f48c0-117">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="f48c0-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f48c0-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f48c0-118">See also</span></span>

- [<span data-ttu-id="f48c0-119">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="f48c0-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f48c0-120">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="f48c0-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f48c0-121">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="f48c0-121">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="f48c0-122">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="f48c0-122">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="f48c0-123">Poziomy ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="f48c0-123">Accessibility Levels</span></span>](./accessibility-levels.md)
- [<span data-ttu-id="f48c0-124">Ograniczenia dotyczące używania poziomów ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="f48c0-124">Restrictions on Using Accessibility Levels</span></span>](./restrictions-on-using-accessibility-levels.md)
- [<span data-ttu-id="f48c0-125">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="f48c0-125">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="f48c0-126">public</span><span class="sxs-lookup"><span data-stu-id="f48c0-126">public</span></span>](./public.md)
- [<span data-ttu-id="f48c0-127">private</span><span class="sxs-lookup"><span data-stu-id="f48c0-127">private</span></span>](./private.md)
- [<span data-ttu-id="f48c0-128">protected</span><span class="sxs-lookup"><span data-stu-id="f48c0-128">protected</span></span>](./protected.md)
- [<span data-ttu-id="f48c0-129">internal</span><span class="sxs-lookup"><span data-stu-id="f48c0-129">internal</span></span>](./internal.md)
