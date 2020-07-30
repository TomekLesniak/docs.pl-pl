---
title: Konwencje kodowania języka c# — Przewodnik programowania w języku C#
description: Dowiedz się więcej na temat konwencji kodowania w języku C#. Konwencje kodowania tworzą spójny wygląd kodu i ułatwiają kopiowanie, zmienianie i konserwowanie kodu.
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
ms.openlocfilehash: 772aebff0b8c7aebe7c7d5c7634cd2931f4570b1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301856"
---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="d3a01-104">konwencje kodowania C# (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="d3a01-104">C# Coding Conventions (C# Programming Guide)</span></span>

<span data-ttu-id="d3a01-105">Konwencje kodowania mają następujące cele:</span><span class="sxs-lookup"><span data-stu-id="d3a01-105">Coding conventions serve the following purposes:</span></span>  
  
- <span data-ttu-id="d3a01-106">Tworzą one spójny wygląd kodu, dzięki czemu czytelnicy mogą skupić się na zawartości, a nie w układzie.</span><span class="sxs-lookup"><span data-stu-id="d3a01-106">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
- <span data-ttu-id="d3a01-107">Umożliwiają one czytelnikom szybsze zrozumienie kodu dzięki założeniu założeń na podstawie poprzedniego środowiska.</span><span class="sxs-lookup"><span data-stu-id="d3a01-107">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
- <span data-ttu-id="d3a01-108">Ułatwiają one kopiowanie, zmienianie i utrzymywanie kodu.</span><span class="sxs-lookup"><span data-stu-id="d3a01-108">They facilitate copying, changing, and maintaining the code.</span></span>  
  
- <span data-ttu-id="d3a01-109">Przedstawiają najlepsze rozwiązania w języku C#.</span><span class="sxs-lookup"><span data-stu-id="d3a01-109">They demonstrate C# best practices.</span></span>  

<span data-ttu-id="d3a01-110">Wskazówki zawarte w tym artykule są używane przez firmę Microsoft do tworzenia przykładów i dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="d3a01-110">The guidelines in this article are used by Microsoft to develop samples and documentation.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="d3a01-111">Konwencje nazewnictwa</span><span class="sxs-lookup"><span data-stu-id="d3a01-111">Naming Conventions</span></span>  
  
- <span data-ttu-id="d3a01-112">W krótkich przykładach, które nie obejmują [dyrektywy using](../../language-reference/keywords/using-directive.md), należy używać kwalifikacji przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="d3a01-112">In short examples that do not include [using directives](../../language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="d3a01-113">Jeśli wiesz, że przestrzeń nazw jest domyślnie importowana w projekcie, nie musisz w pełni kwalifikować nazw z tej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="d3a01-113">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="d3a01-114">Kwalifikowane nazwy mogą być uszkodzone po kropce (.), jeśli są zbyt długie dla pojedynczego wiersza, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="d3a01-114">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
- <span data-ttu-id="d3a01-115">Nie trzeba zmieniać nazw obiektów, które zostały utworzone przy użyciu narzędzi projektanta programu Visual Studio, aby dopasować je do innych wytycznych.</span><span class="sxs-lookup"><span data-stu-id="d3a01-115">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="d3a01-116">Konwencje układu</span><span class="sxs-lookup"><span data-stu-id="d3a01-116">Layout Conventions</span></span>  

<span data-ttu-id="d3a01-117">Dobry układ używa formatowania, aby wyróżnić strukturę kodu i ułatwić odczytywanie kodu.</span><span class="sxs-lookup"><span data-stu-id="d3a01-117">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="d3a01-118">Przykłady i próbki firmy Microsoft są zgodne z następującymi konwencjami:</span><span class="sxs-lookup"><span data-stu-id="d3a01-118">Microsoft examples and samples conform to the following conventions:</span></span>  
  
- <span data-ttu-id="d3a01-119">Użyj domyślnych ustawień edytora kodu (inteligentne wcięcia, cztery znaki wcięcia, karty zapisane jako spacje).</span><span class="sxs-lookup"><span data-stu-id="d3a01-119">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="d3a01-120">Aby uzyskać więcej informacji, zobacz [Opcje, Edytor tekstu, C#, formatowanie](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span><span class="sxs-lookup"><span data-stu-id="d3a01-120">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
- <span data-ttu-id="d3a01-121">Napisz tylko jedną instrukcję na wiersz.</span><span class="sxs-lookup"><span data-stu-id="d3a01-121">Write only one statement per line.</span></span>  
  
- <span data-ttu-id="d3a01-122">Napisz tylko jedną deklarację na wiersz.</span><span class="sxs-lookup"><span data-stu-id="d3a01-122">Write only one declaration per line.</span></span>  
  
- <span data-ttu-id="d3a01-123">Jeśli linie kontynuacji nie mają wcięcia automatycznie, Zwiększ wcięcie z jednego tabulatora (cztery spacje).</span><span class="sxs-lookup"><span data-stu-id="d3a01-123">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
- <span data-ttu-id="d3a01-124">Dodaj co najmniej jeden pusty wiersz między definicjami metod i definicjami właściwości.</span><span class="sxs-lookup"><span data-stu-id="d3a01-124">Add at least one blank line between method definitions and property definitions.</span></span>  
  
- <span data-ttu-id="d3a01-125">Użyj nawiasów, aby tworzyć klauzule w wyrażeniu, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="d3a01-125">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a><span data-ttu-id="d3a01-126">Konwencje komentowania</span><span class="sxs-lookup"><span data-stu-id="d3a01-126">Commenting Conventions</span></span>  
  
- <span data-ttu-id="d3a01-127">Umieść komentarz w osobnym wierszu, a nie na końcu wiersza kodu.</span><span class="sxs-lookup"><span data-stu-id="d3a01-127">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
- <span data-ttu-id="d3a01-128">Zacznij komentować tekst, używając wielkiej litery.</span><span class="sxs-lookup"><span data-stu-id="d3a01-128">Begin comment text with an uppercase letter.</span></span>  
  
- <span data-ttu-id="d3a01-129">Koniec tekstu komentarza z kropką.</span><span class="sxs-lookup"><span data-stu-id="d3a01-129">End comment text with a period.</span></span>  
  
- <span data-ttu-id="d3a01-130">Wstaw jedną spację między ogranicznikiem komentarza (//) i tekstem komentarza, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="d3a01-130">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
- <span data-ttu-id="d3a01-131">Nie twórz sformatowanych bloków gwiazdek wokół komentarzy.</span><span class="sxs-lookup"><span data-stu-id="d3a01-131">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="d3a01-132">Wytyczne dotyczące języka</span><span class="sxs-lookup"><span data-stu-id="d3a01-132">Language Guidelines</span></span>  

<span data-ttu-id="d3a01-133">W poniższych sekcjach opisano sposób, w jaki zespół C# postępuje zgodnie z przygotowaniem przykładów i przykładów kodu.</span><span class="sxs-lookup"><span data-stu-id="d3a01-133">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="d3a01-134">Typ danych ciągu</span><span class="sxs-lookup"><span data-stu-id="d3a01-134">String Data Type</span></span>  
  
- <span data-ttu-id="d3a01-135">Użyj [interpolacji ciągów](../../language-reference/tokens/interpolated.md) , aby połączyć krótkie ciągi, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="d3a01-135">Use [string interpolation](../../language-reference/tokens/interpolated.md) to concatenate short strings, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
- <span data-ttu-id="d3a01-136">Aby dołączyć ciągi w pętlach, szczególnie w przypadku pracy z dużymi ilościami tekstu, użyj <xref:System.Text.StringBuilder> obiektu.</span><span class="sxs-lookup"><span data-stu-id="d3a01-136">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="d3a01-137">Jawnie wpisana zmienna lokalna</span><span class="sxs-lookup"><span data-stu-id="d3a01-137">Implicitly Typed Local Variables</span></span>  
  
- <span data-ttu-id="d3a01-138">Użyj [niejawnego wpisywania](../classes-and-structs/implicitly-typed-local-variables.md) zmiennych lokalnych, gdy typ zmiennej jest oczywisty z prawej strony przypisania lub jeśli dokładny typ nie jest ważny.</span><span class="sxs-lookup"><span data-stu-id="d3a01-138">Use [implicit typing](../classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
- <span data-ttu-id="d3a01-139">Nie należy używać [var](../../language-reference/keywords/var.md) , gdy typ nie jest widoczny po prawej stronie przypisania.</span><span class="sxs-lookup"><span data-stu-id="d3a01-139">Do not use [var](../../language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
- <span data-ttu-id="d3a01-140">Nie należy polegać na nazwie zmiennej, aby określić typ zmiennej.</span><span class="sxs-lookup"><span data-stu-id="d3a01-140">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="d3a01-141">Może nie być poprawna.</span><span class="sxs-lookup"><span data-stu-id="d3a01-141">It might not be correct.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
- <span data-ttu-id="d3a01-142">Należy unikać używania zamiast elementów `var` [dynamicznych](../../language-reference/builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="d3a01-142">Avoid the use of `var` in place of [dynamic](../../language-reference/builtin-types/reference-types.md).</span></span>  
  
- <span data-ttu-id="d3a01-143">Użyj niejawnego wpisywania, aby określić typ zmiennej pętli w pętli [for](../../language-reference/keywords/for.md) .</span><span class="sxs-lookup"><span data-stu-id="d3a01-143">Use implicit typing to determine the type of the loop variable in [for](../../language-reference/keywords/for.md) loops.</span></span>  
  
     <span data-ttu-id="d3a01-144">Poniższy przykład używa niejawnego wpisywania w `for` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="d3a01-144">The following example uses implicit typing in a `for` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  

- <span data-ttu-id="d3a01-145">Nie używaj niejawnego wpisywania, aby określić typ zmiennej pętli w pętlach [foreach](../../language-reference/keywords/foreach-in.md) .</span><span class="sxs-lookup"><span data-stu-id="d3a01-145">Do not use implicit typing to determine the type of the loop variable in [foreach](../../language-reference/keywords/foreach-in.md) loops.</span></span>

     <span data-ttu-id="d3a01-146">Poniższy przykład używa jawnego wpisywania w `foreach` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="d3a01-146">The following example uses explicit typing in a `foreach` statement.</span></span>

     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]

     > [!NOTE]
     > <span data-ttu-id="d3a01-147">Należy zachować ostrożność, aby nie zmieniać przypadkowo typu elementu kolekcji możliwej do iterowania.</span><span class="sxs-lookup"><span data-stu-id="d3a01-147">Be careful not to accidentally change a type of an element of the iterable collection.</span></span> <span data-ttu-id="d3a01-148">Na przykład można łatwo przełączać się od <xref:System.Linq.IQueryable?displayProperty=nameWithType> do <xref:System.Collections.IEnumerable?displayProperty=nameWithType> w `foreach` instrukcji, co zmienia wykonanie zapytania.</span><span class="sxs-lookup"><span data-stu-id="d3a01-148">For example, it is easy to switch from <xref:System.Linq.IQueryable?displayProperty=nameWithType> to <xref:System.Collections.IEnumerable?displayProperty=nameWithType> in a `foreach` statement, which changes the execution of a query.</span></span>

### <a name="unsigned-data-type"></a><span data-ttu-id="d3a01-149">Typ danych bez znaku</span><span class="sxs-lookup"><span data-stu-id="d3a01-149">Unsigned Data Type</span></span>  
  
<span data-ttu-id="d3a01-150">Ogólnie rzecz biorąc, użyj `int` zamiast niepodpisanych typów.</span><span class="sxs-lookup"><span data-stu-id="d3a01-150">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="d3a01-151">Korzystanie z programu `int` jest typowe w całym języku C# i ułatwia korzystanie z innych bibliotek przy użyciu programu `int` .</span><span class="sxs-lookup"><span data-stu-id="d3a01-151">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="d3a01-152">Macierze</span><span class="sxs-lookup"><span data-stu-id="d3a01-152">Arrays</span></span>  
  
<span data-ttu-id="d3a01-153">Użyj zwięzłej składni podczas inicjowania tablic w wierszu deklaracji.</span><span class="sxs-lookup"><span data-stu-id="d3a01-153">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a><span data-ttu-id="d3a01-154">Delegaci</span><span class="sxs-lookup"><span data-stu-id="d3a01-154">Delegates</span></span>  
  
<span data-ttu-id="d3a01-155">Użyj zwięzłej składni, aby utworzyć wystąpienia typu delegata.</span><span class="sxs-lookup"><span data-stu-id="d3a01-155">Use the concise syntax to create instances of a delegate type.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
[!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="d3a01-156">Blok try-catch i przy użyciu instrukcji obsługi wyjątków</span><span class="sxs-lookup"><span data-stu-id="d3a01-156">try-catch and using Statements in Exception Handling</span></span>  
  
- <span data-ttu-id="d3a01-157">Użyj instrukcji [try-catch](../../language-reference/keywords/try-catch.md) dla większości obsługi wyjątków.</span><span class="sxs-lookup"><span data-stu-id="d3a01-157">Use a [try-catch](../../language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
- <span data-ttu-id="d3a01-158">Uprość kod przy użyciu instrukcji języka C# [using](../../language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d3a01-158">Simplify your code by using the C# [using statement](../../language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="d3a01-159">Jeśli masz instrukcję [try-finally](../../language-reference/keywords/try-finally.md) , w której jedyny kod w `finally` bloku jest wywołaniem <xref:System.IDisposable.Dispose%2A> metody, `using` zamiast tego użyj instrukcji.</span><span class="sxs-lookup"><span data-stu-id="d3a01-159">If you have a [try-finally](../../language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="d3a01-160">Operatory && i &#124;&#124; </span><span class="sxs-lookup"><span data-stu-id="d3a01-160">&& and &#124;&#124; Operators</span></span>  
  
<span data-ttu-id="d3a01-161">Aby uniknąć wyjątków i zwiększyć wydajność przez pomijanie niepotrzebnych porównań, użyj [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) zamiast [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) i [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) zamiast [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) podczas wykonywania porównań, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="d3a01-161">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) instead of [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) and [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) instead of [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) when you perform comparisons, as shown in the following example.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a><span data-ttu-id="d3a01-162">Nowy operator</span><span class="sxs-lookup"><span data-stu-id="d3a01-162">New Operator</span></span>  
  
- <span data-ttu-id="d3a01-163">Użyj zwięzłej formy tworzenia wystąpień obiektów z niejawnym wpisywaniem, jak pokazano w poniższej deklaracji.</span><span class="sxs-lookup"><span data-stu-id="d3a01-163">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     <span data-ttu-id="d3a01-164">Poprzedni wiersz jest równoważny z następującą deklaracją.</span><span class="sxs-lookup"><span data-stu-id="d3a01-164">The previous line is equivalent to the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
- <span data-ttu-id="d3a01-165">Użyj inicjatorów obiektów, aby uprościć tworzenie obiektów.</span><span class="sxs-lookup"><span data-stu-id="d3a01-165">Use object initializers to simplify object creation.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a><span data-ttu-id="d3a01-166">Obsługa zdarzeń</span><span class="sxs-lookup"><span data-stu-id="d3a01-166">Event Handling</span></span>  
  
<span data-ttu-id="d3a01-167">W przypadku definiowania programu obsługi zdarzeń, którego nie trzeba później usuwać, należy użyć wyrażenia lambda.</span><span class="sxs-lookup"><span data-stu-id="d3a01-167">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
[!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a><span data-ttu-id="d3a01-168">Statyczne elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="d3a01-168">Static Members</span></span>  
  
<span data-ttu-id="d3a01-169">Wywołaj [statyczne](../../language-reference/keywords/static.md) elementy członkowskie przy użyciu nazwy klasy: *ClassName. StaticMember*.</span><span class="sxs-lookup"><span data-stu-id="d3a01-169">Call [static](../../language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="d3a01-170">Dzięki temu kod jest bardziej czytelny, co oznacza, że statyczny dostęp jest czyszczony.</span><span class="sxs-lookup"><span data-stu-id="d3a01-170">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="d3a01-171">Nie kwalifikuj statycznej składowej zdefiniowanej w klasie bazowej z nazwą klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="d3a01-171">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="d3a01-172">Podczas kompilowania kodu, czytelność kodu jest myląca, a kod może ulec przerwie w przyszłości, jeśli dodasz statyczną składową o tej samej nazwie do klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="d3a01-172">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="d3a01-173">Zapytania LINQ</span><span class="sxs-lookup"><span data-stu-id="d3a01-173">LINQ Queries</span></span>  
  
- <span data-ttu-id="d3a01-174">Użyj znaczących nazw zmiennych zapytania.</span><span class="sxs-lookup"><span data-stu-id="d3a01-174">Use meaningful names for query variables.</span></span> <span data-ttu-id="d3a01-175">Poniższy przykład używa `seattleCustomers` dla klientów, którzy znajdują się w Seattle.</span><span class="sxs-lookup"><span data-stu-id="d3a01-175">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- <span data-ttu-id="d3a01-176">Użyj aliasów, aby upewnić się, że nazwy właściwości typów anonimowych są prawidłowo pisane wielkimi literami przy użyciu wielkości liter w Pascalu.</span><span class="sxs-lookup"><span data-stu-id="d3a01-176">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
- <span data-ttu-id="d3a01-177">Zmień nazwę właściwości, gdy nazwy właściwości w wyniku byłyby niejednoznaczne.</span><span class="sxs-lookup"><span data-stu-id="d3a01-177">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="d3a01-178">Na przykład, jeśli zapytanie zwróci nazwę klienta i identyfikator dystrybutora, zamiast zostawiać je jako `Name` i `ID` w wyniku, należy zmienić ich nazwy, aby wyjaśnić, że `Name` jest nazwą klienta i `ID` jest identyfikatorem dystrybutora.</span><span class="sxs-lookup"><span data-stu-id="d3a01-178">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
- <span data-ttu-id="d3a01-179">Użyj niejawnego wpisywania w deklaracji zmiennych zapytania i zmiennych zakresów.</span><span class="sxs-lookup"><span data-stu-id="d3a01-179">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- <span data-ttu-id="d3a01-180">Wyrównaj klauzule kwerendy pod klauzulą [from](../../language-reference/keywords/from-clause.md) , jak pokazano w poprzednich przykładach.</span><span class="sxs-lookup"><span data-stu-id="d3a01-180">Align query clauses under the [from](../../language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
- <span data-ttu-id="d3a01-181">Użyj klauzul [WHERE](../../language-reference/keywords/where-clause.md) przed innymi klauzulami zapytania, aby upewnić się, że późniejsze klauzule zapytań działają na zmniejszonym, filtrowanym zestawie danych.</span><span class="sxs-lookup"><span data-stu-id="d3a01-181">Use [where](../../language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
- <span data-ttu-id="d3a01-182">`from`Aby uzyskać dostęp do kolekcji wewnętrznych, Użyj wielu klauzul zamiast klauzuli [Join](../../language-reference/keywords/join-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="d3a01-182">Use multiple `from` clauses instead of a [join](../../language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="d3a01-183">Na przykład kolekcja `Student` obiektów może zawierać kolekcję wyników testu.</span><span class="sxs-lookup"><span data-stu-id="d3a01-183">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="d3a01-184">Gdy wykonywane jest następujące zapytanie, zwraca każdy wynik o wartości ponad 90, a także nazwisko studenta, który otrzymał wynik.</span><span class="sxs-lookup"><span data-stu-id="d3a01-184">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a><span data-ttu-id="d3a01-185">Zabezpieczenia</span><span class="sxs-lookup"><span data-stu-id="d3a01-185">Security</span></span>  

<span data-ttu-id="d3a01-186">Postępuj zgodnie z wytycznymi w temacie [zasady bezpiecznego kodowania](../../../standard/security/secure-coding-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="d3a01-186">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3a01-187">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d3a01-187">See also</span></span>

- [<span data-ttu-id="d3a01-188">Visual Basic — Konwencje kodowania</span><span class="sxs-lookup"><span data-stu-id="d3a01-188">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)
- [<span data-ttu-id="d3a01-189">Wytyczne dotyczące bezpiecznego programowania</span><span class="sxs-lookup"><span data-stu-id="d3a01-189">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
